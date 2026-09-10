# Fiche d'un skill distribué — `redaction-actualites-kampus137`

*Un skill est un jeu d'instructions spécialisé, déclenché automatiquement par la reconnaissance d'une intention dans la demande. Il encapsule un savoir-faire réutilisable et impose la forme du livrable.*

## Problème résolu

Avant sa mise en place, chaque article produit nécessitait une seconde demande pour obtenir les éléments de référencement (mot-clé, slug, titre SEO, meta description), puis une troisième pour corriger les liens internes. Le skill impose la livraison du paquet complet dès la première réponse.

## Déclencheurs

« rédige un article », « crée une actualité », « fais-moi un article sur », « nouvelle actualité pour le site », « écris-moi un article ».

## Livrable imposé, à chaque exécution

1. **Un bloc de métadonnées** en tête de fichier — mot-clé principal (expression de 2 à 4 mots en langage courant, ce que les gens tapent réellement), slug (minuscules, sans accents, tirets, mot-clé contigu, vérifié comme non déjà utilisé), titre SEO (commence par le mot-clé exact, se termine par la marque, moins de 60 caractères), meta description (contient le mot-clé exact, moins de 156 caractères).
2. **Le corps de l'article** — le mot-clé dès les premières phrases ; au moins une image avec texte alternatif contenant le mot-clé ; au moins un lien interne réel vers une page d'activité ; une section « Infos pratiques » ; un lien de réservation en fin d'article ; 300 mots minimum ; la mention de date en pied.

## Règles de fiabilité

- Le domaine de billetterie est explicitement qualifié de domaine externe : un lien vers celui-ci ne compte jamais comme lien interne.
- Toute photographie réutilisée est signalée comme telle en légende, pour ne jamais laisser croire qu'un visuel est récent.
- Aucun chiffre inventé dans un bilan ou un retour d'événement : les chiffres réels sont demandés avant rédaction.
- Avant de figer un mot-clé, vérifier le risque de cannibalisation avec un article existant ; si le recoupement est fort, proposer une mise à jour plutôt qu'un nouvel article.

## Règle de marque

La marque reste dans le titre SEO. En revanche, les noms d'espaces inventés en interne ne figurent ni dans le titre, ni dans le slug, ni dans le mot-clé : personne ne les recherche. On utilise les mots génériques réellement tapés — trampoline, escalade, réalité virtuelle, salle de réunion, séminaire entreprise. Les noms d'espaces restent bienvenus dans le corps du texte, là où se construit l'image de marque.

## Preuve de diffusion

Email du 25 juillet 2026 adressé au directeur d'exploitation, objet « Articles (skill & idées) », avec le fichier `.skill` en pièce jointe et un document d'une vingtaine d'idées d'articles classées par thème. Extrait :

> Je viens de mettre en place un système pour que nos actualités sortent toujours avec tout le SEO intégré directement (mot-clé, slug, titre, meta-description), sans repartir de zéro à chaque fois. Deux façons de t'en servir : donne-lui le fichier et demande-lui de l'enregistrer comme skill (il se déclenchera ensuite tout seul), ou colle simplement son contenu au début d'une conversation avant de demander un article — ça marche aussi sans installation.

Le message livre l'outil, son mode d'emploi en deux variantes selon le niveau technique du destinataire, et un backlog de sujets prêt à l'emploi. La version distribuée pesait 3 323 octets ; la version en vigueur au 10 septembre 2026 en compte 5 991 — le skill a été enrichi depuis.

## Les autres skills en service

| Identifiant | Objet | Taille |
|---|---|---|
| `redaction-email-antoine` | Rédaction d'emails dans une voix rédactionnelle identifiée, registre adapté au destinataire | 7 684 car. |
| `journal-decalages` | Journal d'amélioration continue : écarts demande / livraison et réussites à reproduire, classés selon 8 causes | 5 150 car. |
| `diapo-formation-ia` | Régénération des deux présentations de formation pour toute nouvelle personne, à partir d'un questionnaire | 5 401 car. |
