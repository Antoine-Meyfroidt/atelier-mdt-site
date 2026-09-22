# Document de passation — site atelier-mdt.fr

**Établi le 13 septembre 2026 · Antoine Meyfroidt · Atelier MDT**
*SIRET 109 757 526 00016 · antoine@atelier-mdt.fr · 07 43 68 80 97*

Ce document décrit comment le site est construit, où il vit, comment le modifier sans le casser, et ce qui reste en attente. Il s'adresse à moi dans six mois, ou à quelqu'un qui reprendrait la main. Il ne contient aucun mot de passe : les accès sont dans le gestionnaire de mots de passe.

---

## 1. Ce qu'est le site

Un site statique de 23 pages HTML, sans base de données, sans CMS, sans serveur applicatif. Il est hébergé gratuitement par **GitHub Pages** à partir du dépôt public `Antoine-Meyfroidt/atelier-mdt-site`, et servi sur le domaine **atelier-mdt.fr** acheté chez Gandi.

Concrètement : ce qui est dans le dépôt est ce qui est en ligne. Il n'y a pas d'étape de compilation, pas de préproduction, pas de sauvegarde automatique ailleurs que dans l'historique Git.

| | |
|---|---|
| Dépôt | `https://github.com/Antoine-Meyfroidt/atelier-mdt-site` (public) |
| Site | `https://atelier-mdt.fr` |
| Éditeur web | `https://github.dev/Antoine-Meyfroidt/atelier-mdt-site` |
| Hébergement | GitHub Pages, branche `main`, racine du dépôt |
| Domaine et DNS | Gandi LiveDNS · domaine créé le 08/09/2026, expire le 08/09/2027, **renouvellement automatique activé** |
| Liaison domaine → Pages | fichier `CNAME` à la racine du dépôt |
| HTTPS | certificat Let's Encrypt géré par GitHub Pages, automatique |

---

## 2. La règle d'architecture, née d'un incident

**Chaque page est entièrement autonome.** Tout son CSS est dans sa propre balise `<style>`, tout son JavaScript est en ligne à la fin de son `<body>`. **Il n'existe aucun fichier `.css` ou `.js` partagé, et il ne doit pas en exister.**

Cette règle n'est pas une préférence de style. Une tentative de factoriser le CSS commun dans un `assets/site.css` a fait disparaître le bandeau de navigation et le pied de page sur l'ensemble du site : le fichier partagé n'était pas monté au moment du dépôt, et vingt-trois pages se sont cassées d'un coup. Le déploiement se faisant par glisser-déposer manuel, toute dépendance partagée est un point de rupture unique.

Conséquence pratique : modifier le menu ou le pied de page signifie modifier les vingt-trois pages. C'est plus lourd, c'est assumé.

**Les preuves sont dans le HTML.** Sur les huit fiches réalisations, chaque capture d'écran est embarquée en `data:image/webp;base64` et chaque document téléchargeable est lui aussi une data-URI. Aucune de ces pages n'appelle un fichier externe. C'est pourquoi le dossier des fichiers sources a pu être supprimé du dépôt sans rien casser — et c'est aussi pourquoi ces pages sont lourdes (jusqu'à 480 Ko).

---

## 3. Les accès nécessaires

| Service | Sert à quoi | Compte |
|---|---|---|
| GitHub | héberger et publier le site | compte personnel Antoine-Meyfroidt |
| Gandi | domaine, DNS, boîte mail antoine@atelier-mdt.fr | compte Antoine_Meyfroidt |
| Formspree | acheminer le formulaire de contact | formulaire `maeyvaae` |
| Google Search Console | suivi d'indexation | compte Google personnel |
| Google Sheets | classeur de suivi des contacts | compte Google personnel |

---

## 4. Comment mettre le site à jour

1. Modifier le ou les fichiers `.html` en local.
2. Aller sur la page d'accueil du dépôt GitHub.
3. **Add file → Upload files**, déposer les fichiers HTML modifiés, écrire un message de commit, valider.
4. Pour un fichier de `assets/` : **ouvrir d'abord le dossier `assets`** sur GitHub, *puis* Add file → Upload files. Un PDF déposé à la racine ne sera pas trouvé par les pages, qui pointent vers `assets/`.
5. Attendre deux à trois minutes que GitHub Pages redéploie, puis recharger le site avec `Ctrl+F5`.

**Le piège de vscode.dev.** L'éditeur web `github.dev` travaille sur un système de fichiers virtuel : les modifications et les suppressions restent **dans le navigateur** tant qu'elles ne sont pas validées par un **Commit & Push** depuis le panneau Source Control (icône de branche, à gauche). Le badge numérique sur cette icône compte les changements en attente. Fermer l'onglet ou vider les données de navigation avant le commit perd tout le travail. Ce piège a déjà coûté une session entière.

**La vérification après mise à jour** se fait toujours sur une URL avec un paramètre, par exemple `atelier-mdt.fr/offres.html?v=2`, pour contourner le cache. Sans ça, on peut consulter pendant vingt minutes une version périmée en croyant que le dépôt n'a pas fonctionné.

---

## 5. Les interdits

**Ne jamais toucher aux enregistrements MX, TXT SPF et SRV chez Gandi.** Ce sont eux qui font fonctionner la boîte antoine@atelier-mdt.fr. Les modifier ou les supprimer coupe la messagerie, et une erreur de SPF envoie les emails sortants en indésirable sans message d'erreur.

**Ne jamais renommer `404.html`.** GitHub Pages n'utilise la page d'erreur personnalisée que si elle porte exactement ce nom, à la racine.

**Ne jamais supprimer `google525e841bafaa1ec7.html`.** C'est le fichier de vérification de propriété Search Console ; Google le revérifie périodiquement et retire la propriété s'il disparaît.

**Ne jamais créer de fichier CSS ou JS partagé.** Voir section 2.

**Ne jamais écrire « formation » sur le site.** Faute de certification permettant une prise en charge OPCO, le vocabulaire retenu est « accompagnement », « atelier », « module atelier ». Le rendez-vous gratuit s'appelle « Échanger 30 minutes » — pas « diagnostic », pas « échange de qualification ».

---

## 6. L'inventaire

**23 pages HTML**, toutes à la racine du dépôt :

`index` · `realisations` et les 8 fiches `realisation-01` à `realisation-08` · `offres` · `exemples` et les 4 pages par famille (`exemples-automatisation`, `exemples-veille`, `exemples-donnees`, `exemples-ia`) · `rentabilite` · `qui-suis-je` · `contact` · `merci` · `cgv` · `mentions-legales` · `404`.

**Fichiers techniques à la racine** : `CNAME`, `robots.txt`, `sitemap.xml` (21 URL indexables, `merci` et `404` exclues), `google525e841bafaa1ec7.html`.

**Fichiers utilisés dans `assets/`** : `favicon-16.png`, `favicon-32.png`, `favicon-180.png`, `verrouillage-baseline-ambre.png` (image de partage Open Graph), `brochure-atelier-mdt.pdf` (version à lire, 9 pages), `brochure-atelier-mdt-presentation.pdf` (version à montrer, 10 pages), `CGV-Atelier-MDT.pdf`.

---

## 7. Ce qui est branché

**Le formulaire de contact** est envoyé à Formspree en AJAX par un `fetch` JavaScript, puis la page redirige vers `merci.html`. La redirection native et la réponse automatique sont des options payantes de Formspree : c'est pourquoi elle est faite en JavaScript. Un envoi classique en `POST` sert de repli si le JavaScript est désactivé, et un champ `_gotcha` invisible sert de piège à robots.

**`merci.html` annonce un récapitulatif par email** qui n'existe pas encore. Il deviendra vrai le jour où le scénario Make sera en service. Décision du 13/09 : on garde la phrase.

**Google Search Console** est configuré en propriété par préfixe d'URL, vérifiée par fichier HTML, sitemap soumis le 12/09/2026. Un site neuf met généralement d'une à trois semaines à s'indexer complètement, et un sitemap soumis ne garantit pas l'indexation.

---

## 8. Ce qui reste ouvert

**Sur le site**

- `merci.html` promet un récapitulatif par email tant que le scénario Make n'est pas branché.
- Les données structurées JSON-LD ne sont présentes que sur `index.html`.
- Le délai du déploiement IA est annoncé « au devis », faute de référence fiable : le seul cas réel a pris trois mois avec une charge partagée.

**Sur les brochures**

- Page 1 de la version portrait : « Quatre chantiers différents, une seule règle : sur vos outils, documenté, transmis. » C'est faux pour la veille, dont le système tourne chez Atelier MDT. La page 3 le corrige, mais un lecteur qui s'arrête à la couverture repart avec l'idée fausse. Le site, lui, a été corrigé le 13/09.
- Portrait page 8 et paysage page 2 : « pour les trois premiers clients **de chaque offre** », alors que le site dit trois clients au total. Une seule des deux formulations doit survivre.

**Sur les documents de référence**

- `atelier-mdt-decisions.md` contient toujours l'ancienne section 3 : veille en deux offres, tableau de bord sans paliers, mise à jour à 60 €, déploiement à 500 €. C'est le document qu'on ouvre pour chiffrer un devis : tant qu'il n'est pas corrigé, il fait annoncer un mauvais prix.
- La description du projet Claude porte la même grille périmée.
- Les CGV sont en relecture chez l'avocat. À lui signaler : la nouvelle structure du déploiement, le caractère obligatoire de l'atelier, la conservation des documents clients à un an, le changement de rythme de veille gratuit, la réversibilité des veilles, la mise à jour trimestrielle à 150 €, et les deux changements de vocabulaire (article 2 « conclusion du contrat », article 7 « atelier collectif »).

**Deux prix qui n'existent pas encore**

- Le barème de défraiement pour un atelier au-delà de 5 km autour de Rennes. Le site dit « chiffrés dans le devis » ; sans barème, ce chiffre sera improvisé, ce que la règle « jamais de négociation en direct » interdit en pratique.
- Le prix unitaire des modèles réutilisables, vendus hors socle. Le site dit « à l'unité » sans montant.

**Un chiffre à revérifier avant chaque devis**

`offres.html` annonce l'abonnement Claude Team à 20-25 $ par personne et par mois, relevé sur la grille officielle d'Anthropic en septembre 2026. Anthropic facture en dollars et ajuste ses prix : vérifier à la source, ne jamais afficher une conversion en euros issue d'un comparateur.

---

## 9. Ménage possible dans le dépôt

Rien de ce qui suit n'est urgent : ce sont des fichiers inutilisés, pas des erreurs.

**Doublons certains, dans `assets/`** — `brochure-longue-portrait-atelier-mdt.pdf` et `brochure-longue-paysage-atelier-mdt.pdf` sont octet pour octet identiques à `brochure-atelier-mdt.pdf` et `brochure-atelier-mdt-presentation.pdf`. Environ 400 Ko en double.

**Les deux brochures courtes** (`brochure-courte-atelier-mdt.pdf`, `brochure-courte-sombre-atelier-mdt.pdf`) sont dans `assets/` alors qu'elles sont destinées aux pièces jointes de mails froids. Aucune page du site n'y renvoie, donc elles ne seront pas indexées par un lien — mais elles restent téléchargeables par qui connaît l'URL, le dépôt étant public.

**Fichiers à la racine, non appelés par le site** : `avatar-carre-nuit.png`, `favicon-16/32/48/180.png`, `portrait.jpg`, `portrait-A/B/C.jpg`, `portrait-carre.jpg`, `symbole-baseline-encre.png`, `verrouillage-baseline-ambre.png`. Les pages appellent toutes les copies rangées dans `assets/`.

⚠️ **Vérifier avant de supprimer.** `symbole-baseline-encre.png` est le fichier prévu pour la signature email, qui a besoin d'une URL publique. Si la signature pointe vers la copie à la racine, la supprimer casse l'image dans tous les emails envoyés. Même prudence pour les portraits, qui peuvent être utilisés ailleurs qu'ici.

---

## 10. Gandi — état du domaine au 13/09/2026

Le domaine est en LiveDNS chez Gandi, renouvellement automatique activé, expiration le 08/09/2027.

Deux options apparaissent **Inactive** dans le panneau « Domain configuration », et c'est l'état normal par défaut :

**Pack DNS Security+** est un service payant et facultatif de Gandi. D'après leur documentation, il ajoute une validation par email sur les opérations sensibles (déverrouillage du domaine, modification DNS, redirections, changement de propriétaire), une redondance DNS anycast, une sauvegarde illimitée de la zone et un certificat de propriété. Il n'est pas activé par défaut, il n'est pas obligatoire, et ni le site ni la messagerie n'en dépendent. À noter : changer les serveurs de noms le désactive automatiquement.

**DNSSEC** est également inactif, ce qui est l'état par défaut. C'est un durcissement optionnel, sans effet sur le fonctionnement du site ou de la boîte mail. Une activation mal configurée peut en revanche rendre le domaine injoignable : à n'entreprendre que posément, pas un vendredi soir.

---

## 11. Abonnements et lignes

Gandi pour le domaine et la boîte mail. Claude Pro à 21,60 €/mois, renouvelé le 8. Revolut Business, plan gratuit. Abby, compte créé, plan gratuit. **Ligne Free pro à 2 €/mois : conservée** (décision du 13/09/2026, elle avait été envisagée à l'abandon). Make : offre non confirmée, incident de fusion entre le compte Kampus et le compte Atelier MDT, ticket en cours.

Make reste le chemin critique : il bloque les deux prototypes de veille, l'alerte d'échec de scénario, le scénario du formulaire et la branche de facturation.

---

## 12. En cas de problème

**Le site affiche une ancienne version** — recharger avec `Ctrl+F5`, ou ajouter `?v=2` à l'URL. Si c'est encore le cas après cinq minutes, vérifier que le commit est bien passé sur GitHub.

**Le bandeau ou le pied de page a disparu sur une page** — un fichier a été déposé incomplet, ou quelqu'un a extrait le CSS. Reprendre la page depuis le dossier local et la redéposer.

**Un bouton de téléchargement renvoie vers la page 404** — le PDF a été déposé à la racine au lieu de `assets/`.

**Le formulaire ne répond plus** — vérifier le quota mensuel du plan gratuit Formspree, puis que le formulaire `maeyvaae` est toujours actif.

**Un fichier a été supprimé par erreur** — l'historique Git le conserve. Onglet Commits du dépôt, ouvrir le commit d'avant la suppression, récupérer le fichier.

---

*Document établi le 13 septembre 2026. À relire à chaque changement de grille tarifaire ou d'hébergement.*
