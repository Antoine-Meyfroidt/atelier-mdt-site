# Base de connaissances IA — Kampus 137 / Team Building Rennes
### Contenu de référence pour produire les mini-decks « Premiers pas » + « Avancé » par profil
*Version : juillet 2026. Recherche web croisée (sources officielles Anthropic, OpenAI, Google, CNIL + presse tech). Tout ce qui n'est pas solidement vérifié est marqué **« à vérifier »**. Aucun chiffre/version/prix n'a été inventé.*

---

## 0. Comment utiliser cette base

- **Par profil = 2 mini-decks** : un « Premiers pas » (débutant) + un « Avancé ».
- Cette base = la **banque de contenu** (le quoi). Le **gabarit visuel** (le comment : structure, design, nb de slides) sera défini à partir des exemples déjà faits par Antoine.
- **Principe de production** : gabarit fixe → on ne fait que **brancher les exemples pro + perso** de la personne. Chaque nouveau profil = quelques minutes de personnalisation, pas une reconstruction.
- **Règle de calibrage** : un débutant reçoit des **cas d'usage ultra concrets**, pas de théorie. Tokens / ML / agents / skills = réservés au deck « Avancé ».

---

## 1. Méthode de personnalisation (le cœur du dispositif)

Pour chaque nouveau profil, avant de générer les decks, je collecte (ou tu me donnes) :

1. **Métier / rôle** et 2-3 **tâches répétitives** qui lui mangent du temps.
2. **Outils déjà utilisés** (Outlook, Excel, Canva, WhatsApp…).
3. **Appétence tech** (grand débutant ↔ à l'aise).
4. **Angle perso** (1-2 centres d'intérêt : voyage, cuisine, sport, enfants, révisions…).

→ Je sélectionne **3-4 cas d'usage pro + 2-3 perso** qui parlent à CETTE personne, et je les branche dans le gabarit.

### Grille d'archétypes → cas d'usage *(hypothèses de départ, à adapter à chaque vraie personne)*

| Profil type | Cas d'usage PRO parlants | Cas d'usage PERSO parlants |
|---|---|---|
| **Dirigeant / gérant** | Synthèse de docs longs, préparation de RDV, brouillons de décisions, veille concurrentielle sourcée | Rédiger un discours, planifier un voyage, expliquer un sujet complexe simplement |
| **DRH / RH** *(cible B2B)* | Rédiger offres d'emploi, trames d'entretien, synthèse d'enquête interne, reformuler une note RH (⚠️ jamais de CV/données perso dans une IA grand public) | Idées cadeaux, courriers perso, organisation d'événement familial |
| **Membre CSE** *(cible B2B)* | Comparer des devis prestataires, rédiger une communication aux salariés, idées d'activités/arbre de Noël, sondage | Organiser un week-end de groupe, budget, invitations |
| **Commercial / dév.** | Relances, personnalisation d'e-mails, qualification de leads, argumentaires, comptes-rendus de RDV | Négocier un achat, rédiger une annonce (revente), lettre de motivation |
| **Marketing / com** | Déclinaisons de contenu (post/newsletter/résumé), visuels, calendrier éditorial, brainstorming | Retouche photo, montage d'un album, faire-part |
| **Animateur / opérationnel** | Idées d'animations, fiches consignes, réponses types aux familles, scripts d'accueil | Révisions/formation, quiz, organisation perso |
| **Comptable / admin** | Explication de formules Excel, synthèse de contrats, modèles de courriers, tri d'e-mails | Déclarations, courriers administratifs, budget familial |
| **Enseignant / formateur** | Créer des exercices, adapter un cours à un niveau, corriger, générer des quiz | Aide aux devoirs des enfants, apprentissage d'une langue |

*(La cible B2B de Team Building Rennes = DRH, membres de CSE, dirigeants, élus — d'où l'attention particulière sur ces 3 archétypes.)*

---

## 2. BLOC « PREMIERS PAS » (débutant) — banque de contenu

### 2.1 C'est quoi l'IA générative, en une image
Une IA comme ChatGPT / Claude / Gemini, c'est **un collaborateur brillant qui vient d'arriver** : il a énormément lu, écrit vite et bien, mais il ne connaît ni votre contexte, ni vos habitudes, ni vos infos récentes. **Plus vous lui expliquez précisément ce que vous voulez, meilleur est le résultat.** *(Métaphore officielle Anthropic.)*

### 2.2 Ce que ça sait faire / ce qu'il faut vérifier
- **Fort pour** : rédiger et reformuler, résumer, traduire, brainstormer, expliquer simplement, trier/classer, donner une première structure.
- **À toujours vérifier** : chiffres, dates, noms, citations, sources, actualité récente, droit/tarifs. L'IA peut inventer **avec aplomb** (voir 2.6).

### 2.3 Les 4 outils pour démarrer *(voir tableaux détaillés §4 — versions/prix à revérifier)*
1. **ChatGPT** (OpenAI) — le plus polyvalent et grand public.
2. **Le Chat / « Vibe »** (Mistral, **français, hébergé en Europe**) — l'argument souveraineté/RGPD.
3. **Claude** (Anthropic) — rédaction soignée, documents longs.
4. **Gemini** (Google) — intégré à Gmail/Docs/Android.
> Pour débuter : **une version gratuite suffit**. On ne paie que si l'usage devient régulier ou sensible.

### 2.4 Écrire son 1er prompt — la recette simple
**Rôle + Contexte + Tâche + Format.**
> « Tu es [rôle]. Contexte : [situation]. Fais [tâche précise]. Format : [longueur, ton, forme]. »

Et surtout : **on dialogue, on ne commande pas une fois.** « Reformule en plus court », « ton plus chaleureux », « ajoute un exemple » sont des relances normales.

### 2.5 Trois exemples AVANT / APRÈS *(à re-thématiser selon le profil)*
- **E-mail** — AVANT : « Écris un mail de relance. » → APRÈS : « Tu es chargé du dév. commercial d'un centre de loisirs. Un DRH a demandé un devis il y a 10 jours, sans réponse. Rédige une relance : ton cordial, 120 mots max, un seul appel à l'action (proposer un créneau d'appel de 15 min), sans être insistant. »
- **Synthèse** — AVANT : « Résume cette réunion. » → APRÈS : « Voici mes notes brutes (entre """). Fais un compte-rendu en 3 parties : décisions / actions (avec responsable + échéance) / points en suspens. 1 page max, à puces. Si une info manque, écris "à préciser" plutôt que d'inventer. »
- **Idées** — AVANT : « Donne des idées d'animations. » → APRÈS : « Tu es animateur événementiel. On veut remplir nos créneaux de semaine avec des entreprises. Propose 8 idées de team building indoor, 2-4 h, groupes de 15-40 pers. Pour chaque : titre + 1 phrase + bénéfice cohésion. En tableau. »

### 2.6 Trois règles de sécurité (à marteler dès le niveau débutant)
1. **Vérifier avant d'envoyer** : rien ne part à un client / dans un document officiel sans relecture humaine.
2. **Ne jamais coller de données personnelles ou confidentielles** (clients, enfants, RH, contrats) dans une IA grand public gratuite.
3. **L'IA ne connaît pas l'actu récente ni vos tarifs à jour** — préciser la date et exiger des sources pour tout sujet sensible au temps.

---

## 3. BLOC « AVANCÉ » — banque de contenu

### 3.1 Tokens & fenêtre de contexte
**Idée en 1 phrase** : un **token** = un petit morceau de texte (≈ ¾ d'un mot) ; la **fenêtre de contexte** = tout ce que l'IA peut « avoir sous les yeux » d'un coup (sa mémoire de travail).
- Pourquoi ça compte : **coût** (les offres payantes se facturent au token), **longueur max** (au-delà, l'IA « oublie » le début), **mémoire** (l'IA n'a pas de mémoire permanente : on lui renvoie l'historique à chaque fois).
- Ordres de grandeur 2026 *(à vérifier — évolue vite)* : Claude jusqu'à **1 M tokens** ; Gemini 3 Pro **1 M** (2 M annoncé) ; GPT-5.x **~400 K** *(sources divergentes)*. 1 M tokens ≈ 700 000 mots (plusieurs romans).
- ⚠️ **« Context rot »** : une grande fenêtre ne garantit pas un bon raisonnement sur tout le contenu — la précision chute souvent bien avant la limite. **Mieux vaut donner les 20 pages pertinentes que 300 pages.**
- **Analogie** : un bureau de travail. Les tokens = les feuilles ; la fenêtre = la taille du bureau. Trop de dossiers étalés → on ne retrouve plus la bonne info ; bureau plein → chaque nouvelle feuille en fait tomber une ancienne.

### 3.2 Comment « pense » un LLM (machine learning)
**Idée en 1 phrase** : le modèle a appris, en avalant d'énormes quantités de textes, à **prédire le mot suivant le plus probable** — et enchaîne ces prédictions.
- **Deux phases** : *entraînement* (rare, coûteux, fige les connaissances à une date) vs *inférence* (à chaque question ; le modèle n'apprend rien de nouveau).
- **Pourquoi ça hallucine** : il ne « sait » pas les faits, il produit du texte plausible. Face à un trou, il improvise plutôt que de dire « je ne sais pas ». **Fluidité ≠ fiabilité.**
- **Analogie** : un candidat de quiz surdoué qui refuse de dire « je ne sais pas » et improvise une réponse crédible avec le même aplomb que les vraies.

### 3.3 Prompting avancé
- **Few-shot** : donner 3 à 5 exemples de ce qu'on attend (oriente format/ton/structure). *(dosage indicatif Anthropic)*
- **Raisonnement étape par étape** : « procède par étapes », « vérifie avant de conclure ». *(Moins critique sur les modèles récents à « mode réflexion » automatique, mais reste une valeur sûre.)*
- **Chaînage** : découper une tâche complexe en prompts successifs (brouillon → relecture → correction).
- **Fournir ses documents** en contexte, délimités (`"""…"""` pour ChatGPT, balises `<document>` pour Claude) ; placer le doc **avant** la question ; demander à l'IA de **citer les passages** utilisés.
- *Détail dépendant de l'outil* : syntaxe de structuration (XML pour Claude, Markdown/XML pour Gemini, délimiteurs pour ChatGPT). Le principe « séparez clairement les blocs » est universel.

### 3.4 Agents, skills, connecteurs (MCP)
- **Agent vs chatbot** : *« un chatbot répond, un agent accomplit »*. L'agent **planifie → agit (outils) → observe → ajuste** en boucle.
- **Appel d'outils** : le modèle peut appeler un logiciel externe (agenda, e-mail, CRM, web) au lieu de seulement écrire du texte.
- **Skills** : un dossier d'instructions (`SKILL.md`) qui apprend à l'agent une tâche répétable ; ne se charge que quand c'est utile.
- **MCP (Model Context Protocol)** : norme ouverte (Anthropic, fin 2024) = **le « port USB-C de l'IA »** ; un **connecteur** = le câble vers un service (Outlook, SharePoint, CRM…). Standard de fait en 2026, supporté par Claude, ChatGPT, Perplexity, Mistral… *(chiffres d'adoption : à vérifier, sources tierces).*
- ⚠️ **Sécurité** : ne pas laisser un agent tout exécuter en auto-approbation sur des actions sensibles ; n'installer que des connecteurs de confiance.
- **Exemple pro** : un agent branché sur agenda + CRM + messagerie lit les RDV à venir, récupère les infos client, et rédige une relance personnalisée prête à envoyer.

### 3.5 Automatisation no-code (IA + Make / Power Automate / Zapier)
**Principe** : déclencheur (nouvel e-mail, formulaire soumis) → étape(s) IA (résume / classe / rédige) → résultat rangé (tableur, notification, brouillon).
5 automatisations réalistes pour une PME :
1. **Tri/priorisation des e-mails** entrants (commercial / SAV / facture).
2. **Qualification des leads** : note « chaud/froid » 1-10 + enregistrement CRM/tableur *(directement transposable au tri des demandes de séminaires/team building — pipeline Fillout → Make → Excel déjà en place)*.
3. **Déclinaison de contenu** : un texte source → post LinkedIn + newsletter + résumé.
4. **Résumé de documents/réunions** → décisions + actions par e-mail.
5. **Réponses types** (tarifs, dispos) : l'IA rédige un **brouillon**, un humain valide et envoie.
> ⚠️ **Human-in-the-loop** obligatoire sur tout ce qui est sensible/visible client. RGPD art. 22 : pas de décision lourde sur une personne prise **uniquement** par une machine. Les erreurs se **propagent** dans un flux auto → surveillance nécessaire.

---

## 4. Banque d'outils — juillet 2026

> ⚠️ **Volatil** : versions, prix et disponibilités changent tous les 2-3 mois. Prix souvent affichés en $ HT (ajouter conversion € + TVA 20 %). **À revérifier à la date de chaque présentation.**

### 4.1 Assistants généralistes
| Outil | Éditeur | Le mieux pour | Gratuit / Payant *(indicatif)* |
|---|---|---|---|
| **ChatGPT** | OpenAI (US) | Polyvalence grand public, images, voix | Gratuit · Go ~8 € · Plus ~20-23 € · Pro ~103 € |
| **Claude** | Anthropic (US) | Rédaction soignée, docs longs (contexte 1 M) | Gratuit · Pro ~18 € · Max ~90/180 € |
| **Gemini** | Google (US) | Multimodal, intégré Gmail/Docs/Android | Gratuit · Plus ~7,99 € · Pro ~21,99 € · Ultra ~275 € |
| **Copilot** | Microsoft (US) | Intégration Office (Word/Excel/Outlook/Teams) | Gratuit (web) · Pro ~22 € · inclus M365 |
| **Le Chat / « Vibe »** | **Mistral (FR)** | **Souveraineté RGPD + français natif** | Gratuit · Pro ~14,99 € HT |
| **Perplexity** | Perplexity (US) | **Recherche sourcée** (liens cliquables, web live) | Gratuit · Pro ~22 € |

**Repères** : souveraineté/français → **Mistral** · veille sourcée → **Perplexity** · docs/rédaction → **Claude** · polyvalence → **ChatGPT** · déjà Microsoft → **Copilot** · écosystème Google → **Gemini**.

### 4.2 Image
- **Midjourney** (qualité artistique, pas de gratuit) · **GPT Image 2** (meilleur texte dans l'image, DALL·E abandonné) · **Adobe Firefly** (**droits commerciaux garantis** → sécurité juridique com d'entreprise) · **Google « Nano Banana »** (édition conversationnelle + gratuit généreux) · **Ideogram** (roi du texte/affiches) · **Recraft** (logos vectoriels SVG).
- **Repères** : texte dans l'image → Ideogram / Nano Banana / GPT Image 2 · logos → Recraft · sécurité juridique → Firefly · gratuit → Nano Banana.

### 4.3 Vidéo *(critère décisif : disponibilité France/UE)*
- ✅ **Google Veo 3.1** (via Gemini, dispo France, audio natif, 4K) et **Adobe Firefly Video** (sortie « safe ») = **choix sûrs et légaux**.
- ⚠️ **Kling / Hailuo** (éditeurs **chinois**) : bon rapport qualité/prix mais **risque RGPD** avec données clients.
- ❌ **Sora 2** (OpenAI) : **indisponible en France/UE**, produit en repli — à écarter comme socle.

### 4.4 Voix / audio / musique
- **ElevenLabs** (**Paris**, RGPD, voix off/doublage FR excellent) · **Suno Pro** (chansons/jingles téléchargeables, droits commerciaux) · **API OpenAI** (transcription de réunions, la moins chère) · **Google NotebookLM** (transforme un document en **podcast audio**).
- ❌ À éviter : **Play.ht** (fermé) · **Udio** (téléchargement désactivé).

### 4.5 IA bureautique
- **Microsoft 365 Copilot** (payant en plus du socle M365 ; hausse M365 au 1er juillet 2026) · **Google Workspace + Gemini** (**IA désormais incluse** dès Business Standard ~13-14 € → meilleur rapport fonctions/prix PME) · **Canva AI** (com/marketing sans designer, système de crédits) · **Notion AI** (désormais réservé aux plans Business).

### 4.6 Angle Kampus / B2B (souveraineté & conformité)
À mettre en avant comme « sûrs et souverains » pour un public français : **Mistral (Vibe)**, **ElevenLabs**, **Google Veo/Gemini**, **Adobe Firefly**. Points de vigilance à expliciter : outils **chinois** (RGPD), **Sora** (indispo France), **coût réel** des add-ons bureautiques.

---

## 5. Limites & RGPD — check-list entreprise

**À FAIRE ✅**
- Vérifier tout fait/chiffre/citation/source avant diffusion (relecture humaine obligatoire).
- Ancrer les réponses sur vos propres documents (« grounding »).
- Pour un usage pro régulier : offre **Team/Enterprise/API** qui **n'entraîne pas** les modèles sur vos données — **ET** validation RGPD par un référent (DPA, hébergement, conservation).
- Anonymiser avant de saisir. Préciser la date + exiger des sources datées sur sujets sensibles.
- Relire pour détecter les biais (surtout RH & com). Garder l'humain décisionnaire.

**À NE PAS FAIRE ❌**
- Coller des données personnelles/confidentielles dans une IA grand public.
- Publier une sortie IA sans relecture · croire une source juste parce que l'IA l'a citée.
- Faire de l'IA l'unique source de vérité pour une décision importante (juridique, RH, financière).
- Supposer que l'IA connaît l'actu / vos tarifs à jour · déléguer au point de perdre la compétence interne.

**Fait vérifié utile** : par défaut, **OpenAI (Team/Enterprise/API) et Anthropic (offres commerciales) n'entraînent pas** leurs modèles sur les données pro. Les **versions grand public gratuites** ont des règles différentes et **peuvent** utiliser les conversations. *(à re-vérifier par outil/formule, les politiques évoluent — ex. changement des conditions grand public Anthropic le 28/09/2025.)*

---

## 6. Fiabilité — vérifié vs à vérifier

**Confiance élevée** : principes de prompting (identiques chez Anthropic/OpenAI/Google) ; nature des tokens / entraînement vs inférence / cause des hallucinations ; définitions agents/skills/MCP ; context rot ; cadre RGPD (CNIL, art. 22) ; politiques « pas d'entraînement » des offres pro OpenAI & Anthropic ; disponibilité France (Mistral/ElevenLabs/Gemini = OK ; Sora = non).

**À vérifier avant chaque présentation** :
- **Noms/numéros de versions de modèles** (très volatils). *Repère fiable côté Claude : gamme Fable 5 / Opus 4.8 / Sonnet 5 / Haiku 4.5 — un des agents citait « Opus 4.6 / Sonnet 4.5 », probablement périmé ; à reconfirmer.* Côté OpenAI/Google, versions à reconfirmer.
- **Tailles de fenêtres** (GPT-5.x : 400 K vs 512 K selon sources ; Gemini 2 M annoncé).
- **Tous les prix en € TTC** (affichés en $ HT).
- **Statut RGPD/serveurs de Kling & Hailuo** (chinois) ; évolution de **Sora** et de l'export **Udio**.
- **Quotas gratuits** (Gemini images, NotebookLM…) et **dates de coupure** des connaissances.

### Sources principales (fiabilité haute)
- Anthropic — Prompting : platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices · Hallucinations : .../test-and-evaluate/strengthen-guardrails/reduce-hallucinations · Contexte : .../build-with-claude/context-windows · Données : privacy.claude.com/en/articles/7996868 · MCP : anthropic.com/news/model-context-protocol · Skills : anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills
- OpenAI — Prompting : help.openai.com/en/articles/10032626 · Données : openai.com/policies/how-your-data-is-used-to-improve-model-performance
- Google — Prompting Workspace/Gemini : support.google.com/a/users/answer/14200040
- CNIL — IA & RGPD : cnil.fr/fr/les-fiches-pratiques-ia · cnil.fr/fr/ia-et-rgpd-la-cnil-publie-ses-nouvelles-recommandations
- MCP standard : modelcontextprotocol.io
