# Site Atelier MDT — structure multi-pages

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
├── rentabilite.html
├── qui-suis-je.html
├── contact.html
├── cgv.html
├── assets/                             favicons, portrait, image de partage, brochures PDF
└── LISEZ-MOI.md
```

**Pourquoi tout à plat** : lors d'un envoi sur GitHub, des fichiers de même nom dans des dossiers différents peuvent s'écraser. Ici chaque page a un nom unique ; on peut glisser tous les fichiers d'un coup sans risque.

Navigation commune : Réalisations · Offres · Rentabilité · Qui suis-je · [Échanger 30 min]. Pied de page : email · SIRET · Mentions légales · CGV.

## Envoyer sur GitHub

1. Dézipper l'archive.
2. Dépôt → **Add file → Upload files**.
3. Glisser **tous les fichiers `.html`** et le **dossier `assets`** (le dossier lui-même, pas son contenu).
4. **Commit changes**.
5. Vérifier que `index.html` à la racine du dépôt affiche bien l'accueil.

L'ancien dossier `realisations/` du dépôt n'est plus utilisé : il peut rester (aucun lien n'y mène), ou être supprimé fichier par fichier à l'occasion.

## Choix par défaut, à valider

- **« Qui suis-je »** plutôt que « Qui sommes-nous » : l'entreprise est une personne, et le site le dit partout ailleurs. Un pluriel serait incohérent avec le refus des titres inflatés. À changer si tu préfères.
- **Prix affichés en « à partir de »** avec le bandeau « tarifs de lancement, trois premiers clients », comme décidé.
- **La dépendance à l'IA est assumée** dans la page Qui suis-je, section « Avec l'IA, et je le dis ».
- **L'angle « dépenser moins, décider mieux »** remplace toute promesse de chiffre d'affaires, conformément à ton cadrage.

## À compléter avant mise en ligne

| Où | Quoi |
|---|---|
| `contact.html` | **Formulaire** : créer un compte Formspree (gratuit) ou Tally, remplacer `VOTRE_ID` dans l'attribut `action`. Sans cela, le bouton n'envoie rien. |
| `contact.html` | Numéro de téléphone, dès la ligne active |
| `qui-suis-je.html` | **Témoignages** : Adrien Cornu inséré ; modèle HTML en commentaire pour les suivants |
| `cgv.html` | Remplacer par la version définitive après retour de l'avocat, dater, retirer le bandeau « en relecture » |
| `index.html` | SIRET (2 endroits) — hébergeur GitHub Pages déjà renseigné |
| toutes les pages | SIRET dans le pied de page |

## RGPD, puisqu'il y a un formulaire

Le formulaire collecte nom, email, entreprise et message. Une mention d'information figure sous le formulaire. Les données transitent par le prestataire de formulaire choisi : vérifie ses conditions (hébergement, durée de conservation) et mentionne-le dans les mentions légales une fois choisi. Ne stocke pas ces contacts dans un fichier de prospection sans base légale.

---

## Déploiement

## Option A — Cloudflare Pages *(recommandée)*

1. Crée un compte sur `dash.cloudflare.com`
2. **Workers & Pages** → **Create** → **Pages** → **Upload assets**
3. Glisse le dossier `site-atelier-mdt` entier, valide
4. Le site est en ligne sur une adresse en `.pages.dev`
5. **Custom domains** → ajoute `atelier-mdt.fr` et `www.atelier-mdt.fr`
6. Cloudflare t'indique les enregistrements DNS à créer — reporte-les dans **Gandi → atelier-mdt.fr → Enregistrements DNS**

Avantages : gratuit, certificat HTTPS automatique, très rapide, mise à jour par simple nouveau dépôt du dossier.

## Option B — GitHub Pages

1. Crée un dépôt public, par exemple `atelier-mdt-site`
2. Dépose `index.html` et le dossier `assets/` à la racine
3. **Settings** → **Pages** → source : branche `main`, dossier `/root`
4. **Custom domain** → `atelier-mdt.fr`, puis coche *Enforce HTTPS*
5. Chez Gandi, crée un enregistrement `CNAME` pour `www` pointant vers `<ton-pseudo>.github.io`, et les enregistrements `A` de la racine vers les adresses indiquées par GitHub dans sa documentation

Avantages : historique des versions. Inconvénient : un peu plus long à configurer que Cloudflare.

---

## La configuration DNS chez Gandi

Tu iras dans **Nom de domaine → atelier-mdt.fr → Enregistrements DNS**. Attention à un point important : **ne touche pas aux enregistrements existants** de type `MX`, ni au `TXT` qui contient `v=spf1`, ni aux `SRV`. Ce sont ceux de ta boîte mail — les supprimer casserait `antoine@atelier-mdt.fr`.

Tu ne modifieras que l'enregistrement `A` de la racine (`@`) et ajouteras un `CNAME` pour `www`, avec les valeurs exactes fournies par l'hébergeur retenu.

Compte de quelques minutes à quelques heures pour que la propagation soit effective.

---

## Après la mise en ligne

**Vérifier** — le site s'ouvre bien en `https://atelier-mdt.fr`, le favicon apparaît dans l'onglet, les liens d'ancrage de la navigation fonctionnent, l'affichage tient sur téléphone, et le lien de partage affiche correctement le logo sur LinkedIn.

**Déclarer le site** — Google Search Console pour le référencement, et la fiche d'établissement Google si tu veux apparaître dans les recherches locales rennaises.

**Héberger le PNG de la signature** — une fois le site en ligne, `https://atelier-mdt.fr/assets/symbole-baseline-encre.png` devient l'adresse à utiliser dans ta signature email.

---

## Ce que le site ne fait pas, volontairement

**Pas de prix affichés.** Décision actée : les tarifs se donnent au devis, ce qui te laisse ajuster par client et monter sans réimprimer quoi que ce soit.

**Pas de formulaire de contact.** Un lien `mailto:` suffit à ton volume, ne nécessite aucun service tiers et n'entraîne aucune obligation de traitement de données. Un formulaire pourra s'ajouter plus tard si le volume le justifie.

**Pas de blog ni de page par offre.** À ajouter seulement si tu décides d'investir dans le référencement — ce qui n'est pas la priorité aujourd'hui.

**Pas de mesure d'audience.** Ça t'évite le bandeau de cookies et toute déclaration. Si tu veux compter les visites plus tard, choisis un outil sans cookie.

---

*Atelier MDT — Antoine Meyfroidt · antoine@atelier-mdt.fr*
