# Site Atelier MDT — structure et mise à jour

*Version du 12 septembre 2026 — archive complète, 17 pages.*

## Arborescence — tout à plat, aucun nom de fichier en double

```
site-atelier-mdt/
├── index.html                          Accueil
├── realisations.html                   Liste des 8 réalisations
├── realisation-01-anniversaires.html   fiche autonome (images et fichiers intégrés)
├── realisation-02-devis-b2b.html
├── realisation-03-lots.html
├── realisation-04-veille.html
├── realisation-05-data.html
├── realisation-06-ia.html
├── realisation-07-granites.html
├── realisation-08-benchmark.html
├── offres.html
├── rentabilite.html                    (intégrée le 12/09, même traitement que les autres)
├── qui-suis-je.html
├── contact.html                        formulaire Formspree, envoi AJAX → merci.html
├── merci.html                          page de remerciement (noindex)
├── cgv.html
├── mentions-legales.html
├── assets/
│   ├── site.css                        ← navigation, menu mobile, pied de page, bloc d'appel (commun à toutes les pages)
│   ├── site.js                         ← ouverture/fermeture du menu mobile
│   ├── favicon-16.png, favicon-32.png, favicon-180.png
│   ├── verrouillage-baseline-ambre.png image de partage (Open Graph) de toutes les pages
│   ├── brochure-atelier-mdt.pdf
│   └── CGV-Atelier-MDT.pdf
└── LISEZ-MOI.md
```

**Pourquoi tout à plat** : lors d'un envoi sur GitHub, des fichiers de même nom dans des dossiers différents peuvent s'écraser. Ici chaque page a un nom unique ; on peut glisser tous les fichiers d'un coup sans risque.

## Ce qui est commun à toutes les pages — et où le modifier

| Élément | Où | Remarque |
|---|---|---|
| Navigation (liens, bouton « Échanger 30 min », menu mobile) | `assets/site.css` + le bloc `<nav>` de chaque page | Le HTML de la nav est identique sur toutes les pages ; pour ajouter un lien, le faire dans chaque page (16 fois) ou me redemander une passe. |
| Menu mobile (burger, sous 760 px) | `assets/site.css` + `assets/site.js` | Sous 430 px, le bouton « Échanger 30 min » quitte la barre et passe dans le menu déroulant. |
| Pied de page | bloc `<footer>` de chaque page | Gauche : domaines. Droite : email · Mentions légales · CGV. Le SIRET n'y figure plus (il est dans les mentions légales et les CGV). |
| Bloc d'appel jaune de fin de page (`.cta-bloc`) | `assets/site.css` | Tous les blocs pointent vers `contact.html`. |

Les styles propres à chaque page restent dans son `<style>`. **Ne jamais recopier des règles `nav`, `footer` ou `.cta-bloc` dans une page** : elles vivent uniquement dans `site.css`.

## Envoyer sur GitHub

1. Dézipper l'archive.
2. Dépôt → **Add file → Upload files**.
3. Glisser **tous les fichiers `.html`** et le **dossier `assets`** (le dossier lui-même, pas son contenu). GitHub ajoute ou remplace les fichiers par chemin : les PDF, favicons et images déjà présents dans `assets/` ne sont pas touchés.
4. **Commit changes**.
5. Vérifier en ligne : l'accueil s'affiche, le menu mobile s'ouvre sur téléphone, le pied de page ne montre plus le SIRET, `merci.html` s'ouvre.

## Formulaire de contact — comment ça marche

- Envoi vers Formspree (`maeyvaae`) **en JavaScript** : à la réussite, redirection vers `merci.html`. Cette méthode fonctionne sur le plan gratuit ; la redirection « native » de Formspree est réservée aux plans payants.
- Sans JavaScript, le formulaire s'envoie quand même (POST classique) et Formspree affiche sa propre page de confirmation.
- Champ anti-spam `_gotcha` (invisible) : les robots qui le remplissent sont ignorés.
- Champs collectés : nom, email, nom de l'entreprise, nombre de salariés (tranches), activité / domaine, sujet, message.

### À faire pour tenir la promesse de `merci.html`

La page merci dit : « Vous recevrez un récapitulatif par mail. » **Ce n'est pas encore vrai.** L'email automatique au visiteur (autoresponse) est réservé aux plans Formspree Professional et Business. Deux options :

1. Construire un scénario Make / Power Automate qui lit la notification Formspree reçue dans la boîte antoine@atelier-mdt.fr et renvoie un récapitulatif au visiteur (même logique que la réalisation 01). **Décision prise : cette option.**
2. Ou retirer la phrase de `merci.html` tant que le flux n'est pas en production.

## RGPD — ce que le site dit, et ce qu'il faut tenir

- Les données du formulaire sont annoncées comme **conservées trois ans à compter du dernier contact** dans un outil de suivi commercial, puis supprimées. C'est la durée recommandée par la CNIL pour les prospects.
- Formspree est nommé comme sous-traitant (hébergement AWS États-Unis, clauses contractuelles types).
- **À compléter dès que l'outil CRM est choisi** : son nom et son pays d'hébergement dans `mentions-legales.html`, section « Données personnelles » (un commentaire HTML `À COMPLÉTER` marque l'endroit).
- Les mentions légales signalent que Google Fonts transmet l'adresse IP du visiteur à Google. Pour éviter ce transfert, héberger la police Manrope dans `assets/` (un fichier `.woff2` et une règle `@font-face`).
- Ces textes ont été rédigés avec soin mais **n'ont pas été relus par un professionnel du droit**. À faire relire avec les CGV.

## CGV

Version du 11 septembre 2026, en relecture. Le mot « formation » a été remplacé par « atelier » (article 7) et « conclusion du contrat » (article 2) : **signaler ces deux changements à l'avocat**, qui relit une version datée du 8 septembre. Quand la version définitive arrive : remplacer le texte, dater, retirer le bandeau « EN RELECTURE », régénérer `assets/CGV-Atelier-MDT.pdf`.

## Choix éditoriaux en vigueur

- « Qui suis-je » plutôt que « Qui sommes-nous » : l'entreprise est une personne.
- Prix affichés en « à partir de », bandeau « prix de lancement, trois premiers clients ».
- Le mot **« formation » n'apparaît nulle part** (cadre réglementaire non clarifié) : « atelier », « accompagnement », « support ». À maintenir dans tout nouveau texte.
- La veille hebdomadaire est présentée comme **formule de base** (5 concurrents ou 3 établissements) ; d'autres formules viendront plus tard.
- Angle « dépenser moins, décider mieux » : aucune promesse de chiffre d'affaires.
- Pas de mesure d'audience, pas de cookie, donc pas de bandeau.
- Pas de blog ni de page par offre tant que le référencement n'est pas une priorité.

## Après chaque mise en ligne

Vérifier : `https://atelier-mdt.fr` s'ouvre, favicon présent, menu mobile fonctionnel, partage d'un lien (offres, fiche) sur LinkedIn affiche image et description, formulaire testé une fois avec une vraie adresse.

---

*Atelier MDT — Antoine Meyfroidt · antoine@atelier-mdt.fr*
