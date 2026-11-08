# Bascule du formulaire de contact : Make déclenché par la notification Formspree

*Préparée le 7 novembre 2026, mise à jour le même jour après la création du scénario. Aucune adresse de webhook, de mailhook ni aucune clé dans ce document, par règle.*

## Pourquoi

Jusqu'ici, `contact.html` envoyait chaque demande en parallèle à Formspree et à un webhook Make, avec une clé lisible dans le code de la page (et dans l'historique public du dépôt depuis le 27/09). Avec ces deux éléments, n'importe qui pouvait faire envoyer l'accusé de réception depuis antoine@atelier-mdt.fr à n'importe quelle adresse.

Désormais la page n'appelle plus Make. Formspree envoie sa notification comme avant ; un filtre Gmail la transfère à une adresse de réception Make (mailhook) ; le scénario lit les champs dans l'email, remplit `Demandes` et envoie l'accusé. Une fois l'ancien webhook supprimé, la clé visible dans l'historique ne sert plus à rien.

Principe inchangé : si Make tombe, la demande reste chez Formspree et dans Gmail.

## Ce qui a été vérifié

- La notification Formspree du 01/11 (test) : expéditeur `noreply@formspree.io`, objet « Demande de contact — atelier-mdt.fr », version texte avec chaque champ sous la forme `nom du champ:` puis la valeur à la ligne suivante, dans l'ordre du formulaire, puis « Submitted … ».
- Le motif ci-dessous a été testé sur cette notification, et sur une version remplie avec un message de plusieurs lignes contenant « nom: » et « email: » : tous les champs sortent correctement.
- Hypothèse à confirmer au premier essai (étape 2.2) : le champ `Text` du mailhook Make contient bien la version texte de l'email, et l'expéditeur arrive bien dans `From › Email address` (champs confirmés par la documentation du module Make le 07/11 ; reste à le voir sur un vrai message transféré).

## Étapes, dans cet ordre

### 1. Le nouveau scénario — fait le 07/11 par Claude, inactif

Créés dans Make (équipe Atelier MDT), sans rien activer ni modifier de l'existant :

- le mailhook **« Notification Formspree (formulaire atelier-mdt.fr) »** : son adresse se lit dans Make → *Webhooks* → ce mailhook → *Copy address to clipboard*. **Ne la recopier dans aucun document** ;
- le scénario **« Formulaire atelier-mdt.fr (via notification Formspree) → Demandes + accusé »** (n° 8433946), **inactif** :
  1. mailhook ;
  2. Text parser › Match pattern sur le champ `Text` du mailhook (motif ci-dessous, sensible à la casse : non, aucune autre option) ;
  3. filtre « Notification Formspree légitime » : expéditeur (`From › Email address`) égal à `noreply@formspree.io` **et** email du formulaire au bon format ; puis Google Sheets › Add a row dans `Demandes`, mêmes colonnes et mêmes formules qu'avant ;
  4. Gmail › Send an email : l'accusé de réception, texte identique à l'actuel, envoyé à l'email du formulaire.

À régler par toi dans Make, car l'outil de Claude ne permet pas ce réglage : dans le scénario, icône d'horloge (*Scheduling*) → *Immediately as data arrives* → **2** exécutions par minute au plus, comme l'ancien. *Save*.

### 2. Transférer la notification depuis Gmail

1. Gmail (meyfroidt.antoine01@gmail.com) → Paramètres → *Transfert et POP/IMAP* → *Ajouter une adresse de transfert* → l'adresse du mailhook.
2. Gmail envoie un code de confirmation au mailhook. Le scénario étant inactif, le message attend dans la file du mailhook : Claude peut lire le code depuis Make, ou toi via *Run once* dans le scénario (le code apparaît dans la bulle de sortie du mailhook ; le scénario s'arrête ensuite au Text parser, c'est normal). Saisir le code dans Gmail. **Ne pas activer le transfert de tout le courrier** : laisser « Désactiver le transfert ».
3. Gmail → Créer un filtre : *De* `noreply@formspree.io`, *Objet* `Demande de contact` → *Transférer à* l'adresse du mailhook. Les libellés existants restent.

### 3. Mettre en ligne la nouvelle page contact et basculer (à enchaîner)

1. GitHub : déposer `contact.html` (lot du 07/11).
2. Make : **désactiver** l'ancien scénario 7627208, **activer** le nouveau.
3. Test depuis une adresse tierce : ligne « Nouvelle » dans `Demandes`, accusé reçu, notification Formspree dans Gmail. Puis supprimer la ligne de test.

### 4. Fermer l'ancien accès

Une fois le test réussi : Make → *Webhooks* → l'ancien webhook du formulaire (celui de l'ancien scénario) → **Delete**. L'ancien scénario peut rester désactivé quelques jours puis être supprimé.

## Motif (Text parser › Match pattern)

```
prenom:\r?\n(?<prenom>[^\r\n]*)[\s\S]*?\r?\nnom:\r?\n(?<nom>[^\r\n]*)[\s\S]*?\r?\nemail:\r?\n(?<email>[^\r\n]*)[\s\S]*?\r?\nactivite:\r?\n(?<activite>[^\r\n]*)[\s\S]*?\r?\ntelephone:\r?\n(?<telephone>[^\r\n]*)[\s\S]*?\r?\nentreprise:\r?\n(?<entreprise>[^\r\n]*)[\s\S]*?\r?\neffectif:\r?\n(?<effectif>[^\r\n]*)[\s\S]*?\r?\nsujet:\r?\n(?<sujet>[^\r\n]*)[\s\S]*?\r?\nmessage:\r?\n(?<message>[\s\S]*?)\s*\r?\nSubmitted \d
```

## Limites à connaître

- Le motif suit l'ordre des champs du formulaire. Si un champ est ajouté, retiré ou déplacé dans `contact.html`, le motif doit être mis à jour, sinon le scénario s'arrête au Text parser (rien n'est perdu : la notification reste dans Gmail).
- Si Formspree change la mise en forme de ses notifications, même effet : l'historique Make montre l'arrêt au Text parser.
- Une opération Make de plus par demande (le Text parser) : 4 au lieu de 3.
- La connexion Gmail de Make expire toujours tous les six mois (prochaine échéance le 09/04/2027).
- Les mentions légales ne changent pas : mêmes destinataires (Formspree, Google, Make).
