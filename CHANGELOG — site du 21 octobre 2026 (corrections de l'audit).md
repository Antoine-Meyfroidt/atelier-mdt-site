# CHANGELOG — site du 21 octobre 2026 (corrections de l'audit)

**Objet : les corrections A, B, C et D de l'audit « face au marché », décidées par Antoine le 20/10 au soir.**

Construit sur `main` du 20/10 à 22 h 32 (commit `d453bfb`, après la fusion n° 4 : blog et accueil v3). Préparé depuis le compte Kampus (crédits du compte perso épuisés).

Ce dossier remplace `2026-10-21 - contact (à valider)`, dont il reprend les trois fichiers : l'ancien dossier peut partir dans `_archive` ou être supprimé.

**À déposer quand tu le décides.** Si `main` a bougé d'ici là, ne dépose pas : fais d'abord reconstruire le lot sur la nouvelle version.

## Ce qui change — 9 fichiers

| Fichier | Changement | Point de l'audit |
| --- | --- | --- |
| `contact.html` | 4 champs visibles (prénom, nom, email, activité). Téléphone, entreprise, effectif, sujet et message passent sous « Préciser votre demande (facultatif) ». « Ce qui vous prend du temps » démarre sur « Choisir… ». | D1 |
| `404.html` | « Contact » devient « Échanger 30 minutes ». Pied de page aligné sur les autres pages : téléphone, LinkedIn, Questions fréquentes, CGV. | D2 |
| `offres.html` | Thème supplémentaire : « +150 € HT à l'installation, puis +35, +40 ou +50 € HT par mois selon le rythme », aux deux endroits. Interruption de quatre semaines par an au plus, annoncée au moins quinze jours avant, non facturée. « Deux jours ouvrés » pour le questionnaire. Appels d'offres : « Territoire supplémentaire : +25 € HT par mois, sans frais d'installation ». | A2/B1, A6, A5, B2 |
| `questions.html` | La même phrase d'interruption, dans la réponse et dans son JSON-LD. | A6 |
| `exemples-ia.html` | « Retourné deux jours ouvrés avant la séance ». | A5 |
| `rentabilite.html` | « Deux supports personnalisés ». « Ce qui mérite votre attention » au lieu de « ce qui mérite une action ». La tuile « 0 semaine manquée » devient « 0 semaine payée sans rapport : le relevé tourne seul, et une pause de ma part, quatre semaines par an au plus, ne vous est pas facturée ». | A1, A3, A6 |
| `realisation-04-veille.html` | « La veille proposée en abonnement dit ce qui a bougé et met en avant ce qui compte le plus, sans recommander d'action. » La description du rapport d'origine (qui contenait des conseils) n'est pas touchée. | A3 |
| `mentions-legales.html` | Téléphone de l'hébergeur : « tél. +1 877 448 4820 » (ligne commerciale de GitHub Enterprise, retenue faute de mieux). Une phrase sur le stockage de session du formulaire, dans le paragraphe Cookies. Date : « mise à jour du 21 octobre 2026 ». | C1, C2 |
| `sitemap.xml` | `lastmod` au 2026-10-21 pour les sept pages indexées ci-dessus. | — |

Rien à modifier dans Make ni dans le classeur : les noms des champs du formulaire sont inchangés. Seul effet : la colonne « Sujet déclaré » reste vide quand le visiteur ne choisit rien (avant, la première option partait par défaut).

## Volontairement non touché

- **CGV** (page et PDF) : rien ne change sans l'avocat (voir plus bas).
- **Brochures** : en attente, décision du 20/10.
- **C3** (recherche préalable de la routine R4) : non traité, faute de savoir ce que R4 consulte et combien de temps elle garde le résultat.
- `merci.html`, les articles, l'accueil.

## Point d'attention

Tant que l'avocat n'a pas modifié l'article 6.6, le site promet plus que les CGV : il dit les semaines d'interruption « non facturées », les CGV disent « les mensualités restent dues ». L'écart joue en faveur du client, mais c'est une contradiction tant que les CGV ne sont pas à jour. Hypothèse (à confirmer par l'avocat) : en cas de litige, la promesse la plus favorable au client risque d'être retenue. Tu t'y tiens donc dès la mise en ligne.

## Vérifié avant dépôt

- Site complet reconstruit (`main` + ces 9 fichiers) : aucun lien interne ni aucune ancre cassés, JSON-LD valides, sitemap valide.
- Rendu des 8 pages modifiées en 1 280 et 390 px : aucun défilement horizontal, aucune erreur de script.
- Formulaire : envoi simulé (intercepté, rien n'est parti) : les 11 champs partent vers Formspree et vers Make, puis la page bascule sur `merci.html`.
- Aucun mot interdit par R2 ajouté. Les seules occurrences de « formation » sont dans « informations ».

## Mise en ligne

1. Sur la page du dépôt, branche `main` : Add file → Upload files → glisser les 9 fichiers `.html` et `.xml` de ce dossier (pas le CHANGELOG).
2. En bas, laisser « Commit directly to the main branch », message « Corrections de l'audit du 20/10 », puis Commit changes.
3. Si tu déposes un autre jour que le 21/10, fais d'abord mettre la date du jour dans `sitemap.xml`.

## Vérifier après, dix minutes plus tard

1. `atelier-mdt.fr/contact.html?v=2` sur téléphone : 4 champs, le lien « Préciser votre demande » s'ouvre.
2. **Envoi de test depuis une adresse tierce** : ligne dans le classeur, accusé de réception reçu, calendrier prérempli sur `merci.html`. Puis supprimer la ligne de test.
3. `atelier-mdt.fr/offres.html?v=2` : les prix du thème supplémentaire et du territoire supplémentaire.
4. Une adresse inexistante, par exemple `atelier-mdt.fr/test-404` : « Échanger 30 minutes » et le téléphone en bas.
5. Search Console : renvoyer `sitemap.xml`.

## Pour l'avocat (relance du 31/10)

Propositions de rédaction, à faire valider : ce n'est pas un avis juridique.

**Article 6.6, aligné sur 6.8.6 (décision du 20/10)**
> 6.6 Interruption exceptionnelle. Le Prestataire pourra suspendre temporairement les livraisons pour une durée cumulée de quatre (4) semaines maximum par année civile, notamment en période de congés, sous réserve d'en informer le Client au moins quinze (15) jours à l'avance. La part de la mensualité correspondant à la période d'interruption n'est pas due et est déduite au prorata de la facture suivante. La prestation reprend automatiquement à l'issue de la période d'interruption.

L'article 6.8.6 reste une dérogation pour les appels d'offres (préavis de trente jours, liste des consultations remise avant l'interruption).

**Article 7.3 et clause de cession** : retirer les modèles réutilisables, sortis de l'offre depuis le 05/10.

**Article 6.8.2** : l'extension de territoire a désormais un prix (+25 € HT par mois et par territoire, sans frais d'installation). « Au tarif indiqué au devis » peut rester, ou devenir « selon la grille tarifaire en vigueur », comme pour le thème supplémentaire.

**Mentions légales** : le téléphone de l'hébergeur retenu (ligne commerciale de GitHub Enterprise, relevée par un site tiers et non vérifiée sur une page de GitHub), et la phrase sur le stockage de session.
