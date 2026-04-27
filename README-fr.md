# audit-ux

> Une skill de cadrage structuré pour les projets de refonte de site web. Elle force les décisions stratégiques avant la première maquette et produit un document de cadrage interne défendable.

**Statut** : testée en conditions réelles sur plusieurs sites avant publication. Disponible en français. Les contributions de traduction anglaise sont bienvenues.

**Licence** : à déterminer. Pour l'instant, usage libre, attribution appréciée.

---

## Le scénario que la skill résout

Vous recevez un brief client de refonte. Le brief peut être réduit à une phrase ou détaillé sur vingt pages. Vous avez peut-être des heatmaps, peut-être pas. Le client peut savoir ce qu'il veut, ou pas. La matière disponible est rarement complète et presque jamais celle qu'on aurait imaginée.

Cette skill produit un document de cadrage solide à partir de cette matière variable, quelle qu'en soit la quantité ou la qualité initiale. Elle pose les bonnes questions au bon moment, signale ce qui manque, force les arbitrages que vous auriez tendance à reporter, et conclut par un livrable qui sert de socle à la direction artistique et au chiffrage.

---

## Ce qu'elle fait, ce qu'elle ne fait pas

**Elle fait :**

- Forcer les décisions stratégiques avant tout choix visuel : pas de plan de sections sans persona tranché, pas de plan de sections sans analyse concurrence, pas de synthèse sans check de complétude
- Vous challenger quand vous prenez un raccourci, par exemple si vous proposez une solution avant d'avoir vraiment diagnostiqué le problème, ou si vous sautez l'analyse concurrence pour aller directement à la maquette
- Vous protéger des erreurs classiques de cadrage : pas d'affirmation confiante sur ce qu'un site n'a pas alors que vous n'avez crawlé qu'une partie, pas de statistique inventée, pas de finding qui ressemble à un fait alors que c'est une hypothèse
- Produire un document de cadrage interne avec verdict stratégique, persona tranché, sitemap cible, plan de sections, décisions structurelles, liste priorisée des bugs avec scoring impact x effort

**Elle ne fait pas :**

- Générer un design system
- Écrire une stratégie de marque
- Remplacer la recherche utilisateur
- Produire une proposition commerciale ou un devis
- Estimer les délais projet
- Auditer la conformité WCAG de manière exhaustive

Elle fait une chose et la fait bien : le cadrage en amont du redesign.

---

## Pour qui

La skill est conçue pour les professionnels qui traitent un brief client payant de refonte :

- Designers indépendants (web, marque, produit)
- Studios et petites agences
- Consultants freelance en stratégie ou marketing
- Designers internes recevant des briefs de parties prenantes
- Stratèges et consultants en marque solo

Elle fonctionne quel que soit votre format de prestation (projet, retainer, mix) et quel que soit le profil de votre client (startup, PME, institution, association).

Elle ne convient pas à la critique informelle d'un site, aux audits prospectifs sortants, à l'analyse concurrentielle isolée, ni à l'auto-audit informel. Pour ces cas, la skill signale le décalage et demande confirmation avant de dérouler.

---

## Installation

> Instructions à jour en avril 2026. Si vous lisez ceci plus tard, vérifiez la documentation officielle Anthropic. Le mécanisme exact peut avoir évolué.

La skill peut s'installer dans deux environnements selon votre usage : Claude.ai (web, mobile, desktop) et Claude Code (CLI). Le fonctionnement diffère dans chaque cas.

### Pour Claude.ai

Prérequis : un compte Claude (plans Free, Pro, Max, Team ou Enterprise) avec l'option *Code execution and file creation* activée dans `Settings > Capabilities`.

1. Cloner ce repo en local, ou télécharger les fichiers en archive ZIP depuis GitHub
2. S'assurer que le dossier racine se nomme bien `audit-ux` et qu'il contient le fichier `SKILL.md` à sa racine. Le nom du dossier doit être identique à la valeur du champ `name` dans la frontmatter du SKILL.md
3. Compresser ce dossier en un fichier `audit-ux.zip`. L'archive doit contenir le dossier, pas seulement les fichiers à plat
4. Aller dans `Customize > Skills` sur Claude.ai
5. Cliquer sur le bouton "+" puis sur *"+ Create skill"* puis sélectionner *"Upload a skill"*
6. Uploader le fichier ZIP. La skill apparaît dans votre liste, à activer avec le toggle

Une fois installée, invoquez la skill avec `/audit-ux` au début d'une nouvelle conversation.

### Pour Claude Code

Prérequis : Claude Code installé (la version supportant les skills, sortie en bêta fin 2025).

```bash
# Pour une installation personnelle (disponible dans tous vos projets)
mkdir -p ~/.claude/skills
cd ~/.claude/skills
git clone https://github.com/FWBFstudio/ux-audit-skill.git audit-ux

# Ou pour une installation au niveau d'un projet spécifique
cd /chemin/vers/votre/projet
mkdir -p .claude/skills
git clone https://github.com/VOTRE-USERNAME/ux-audit-skill.git .claude/skills/audit-ux
```

Claude Code détecte automatiquement la skill et la rend disponible avec `/audit-ux`. Pas besoin de redémarrage tant que le dossier `~/.claude/skills/` existait déjà au démarrage de la session.

### Pour l'API

Les skills sont disponibles via l'outil de code execution de l'API Anthropic. Référez-vous à la [documentation API officielle](https://docs.claude.com/en/docs/intro) pour le détail de l'intégration. Le mécanisme évolue régulièrement.

### Vérifier que l'installation a fonctionné

Démarrez une nouvelle conversation (claude.ai ou Claude Code) et tapez :

```
/audit-ux
```

La skill doit répondre par sa présentation initiale et lancer la phase d'Étape 0 (cartographie de l'état des matières disponibles).

Si rien ne se passe, voyez la section troubleshooting de la [doc Anthropic](https://support.claude.com/en/articles/12512180-use-skills-in-claude). Typiquement : code execution désactivé, nom du dossier non aligné avec le `name` du SKILL.md, ou archive ZIP qui contient les fichiers à plat au lieu d'un dossier.

---

## Sur quels socles méthodologiques elle s'appuie

La skill mobilise des références reconnues, organisées en trois tiers chargés à la demande selon les phases du cadrage. Aucune de ces références n'est appliquée mécaniquement. La skill choisit ce qui sert le cas et écarte ce qui n'est pas pertinent.

**Tier 1, Fondamentaux UX et accessibilité**

- Heuristiques de Nielsen
- Lois de l'UX (Hick, Fitts, Jakob, Miller, von Restorff, etc.)
- Principes de Krug (scannabilité, hiérarchie)
- Référentiels d'accessibilité selon le contexte juridique : WCAG 2.2, European Accessibility Act (UE), ADA (États-Unis), AODA (Ontario), Section 508 (fédéral américain), RGAA (France)

**Tier 2, Conversion et copywriting**

- Joanna Wiebe / Copyhackers (méthode Voice of Customer, structures PAS et 4U)
- Harry Dry / Marketing Examples (specific over vague, show don't tell)
- Alex Hormozi (méthode value stack, *$100M Offers*)
- Donald Miller (StoryBrand, le client est le héros, le guide qui le rassure)

**Tier 3, Positionnement et différenciation**

- April Dunford (*Obviously Awesome*, alternatives concurrentielles, catégorie de marché)
- Strategyzer / Alexander Osterwalder (Value Proposition Canvas : jobs, pains, gains)

Chaque tier porte une note explicite sur la signature culturelle de ses références. Les frameworks marketing nord-américains (Hormozi, Miller) sont signalés comme tels et la skill invite à les filtrer selon le contexte client. Un cadrage pour un fabricant artisanal français ne mobilise pas les mêmes outils qu'un cadrage pour une scale-up SaaS B2B.

---

## Comment elle fonctionne

### Invocation

```
/audit-ux
```

La skill se déclenche uniquement sur cette commande explicite. Elle ne réagit pas à des questions UX génériques ni à des discussions informelles sur des sites web.

### Configuration à la première invocation

À votre toute première invocation, la skill détecte qu'aucune posture professionnelle n'est connue et propose un calibrage optionnel en trois questions courtes :

1. Quelle est la conviction stratégique que vous portez et que vous ne négociez pas, même si le client pousse dans l'autre sens ?
2. Pour quelle catégorie de clients ne travaillez-vous pas, c'est-à-dire ceux que vous savez ne pas pouvoir bien servir ?
3. Quel est votre format de prestation principal : projet ponctuel forfaitaire, retainer, mix, ou autre ?

Vous pouvez répondre aux trois, à certaines, ou taper *"skip"* pour démarrer en posture neutre. Les réponses sont stockées pour les sessions suivantes et colorent les recommandations.

### Aller plus loin : adjoindre un fichier descriptif de votre activité

Le calibrage en trois questions est une entrée minimale. Si vous voulez que la skill colore vraiment ses recommandations selon votre identité professionnelle (positionnement, références créatives, anti-patterns identitaires, ton, etc.), vous pouvez lui adjoindre un fichier markdown descriptif de votre studio, agence, ou pratique. Le contenu de ce fichier vous appartient. Écrivez ce qui compte pour vous.

Trois manières de l'utiliser :

1. **Le coller en début de conversation.** Au moment d'invoquer `/audit-ux`, collez le contenu de votre fichier descriptif juste avant. La skill le lira et l'intégrera dans sa posture pour cette session.

2. **Le placer dans un Project Claude.ai (plan Pro et plus).** Créez un Project dédié à vos cadrages clients dans Claude.ai, et placez votre fichier descriptif comme document de contexte du Project. Il sera automatiquement chargé à chaque conversation initiée dans ce Project.

3. **Créer une skill d'identité professionnelle séparée.** Pour les utilisateurs qui veulent une vraie modularité, créez une seconde skill (par exemple `mon-studio-identite`) que vous activez en parallèle de `audit-ux`. Claude composera automatiquement les deux.

### Le workflow en cinq phases

Une fois invoquée, la skill cartographie le projet sur cinq phases et détecte où vous en êtes :

1. **Intake** : brief client, scope commandé, confirmation de posture
2. **Analyse de l'existant** : captures d'écran, heatmaps si disponibles, substituts comportementaux sinon, check-up technique
3. **Analyse concurrence** : deux à trois concurrents, positionnement
4. **Questions stratégiques** : géographie, mix des cibles, KPIs, persona, alternatives mentales du client, changements de gouvernance, capacité opérationnelle
5. **Synthèse** : check de complétude, choix entre Voie 1 (cadrage complet) et Voie 2 (cadrage hypothétique avec hypothèses marquées), puis rédaction

La skill n'impose pas de séquence linéaire. Elle détecte ce que vous avez partagé, pose les questions de la phase concernée, et refuse de sauter en avant quand de la matière fondatrice manque.

### Voie 1 / Voie 2 : gestion des briefs anémiques

Les briefs sont souvent anémiques en pratique. La skill gère cette réalité avec deux voies :

- **Voie 1** : matière suffisante, décisions fermes, livrable défendable directement
- **Voie 2** : matière partielle, cadrage hypothétique avec hypothèses structurantes explicitement marquées (H1, H2, etc.), à valider avec le client avant production

L'en-tête du livrable nomme la voie utilisée, ce qui permet au client et à vous d'évaluer en un coup d'œil la fiabilité du cadrage.

### Livrable

La skill produit un document de cadrage en markdown contenant :

- Verdict stratégique (une page maximum) : ce qui cloche, ce qui doit rester, le pari stratégique, recommandation d'extension de scope si nécessaire
- Persona principal tranché : un ou deux personas avec axe de différenciation choisi pour le contexte
- Sitemap cible : pages ajoutées, supprimées, fusionnées, avec justifications
- Plan de sections : home plus deux à trois pages tunnels critiques
- Décisions structurelles non négociables : cinq à huit choix qui orientent la direction artistique
- Liste des bugs critiques avec scoring impact x effort et timing de correction
- Passation vers la direction artistique : contraintes identitaires, contraintes structurelles, anti-patterns sectoriels et identitaires à exclure

Ce document est interne. Il sert de socle à la direction artistique, au chiffrage, et à la proposition commerciale. Il n'est pas conçu pour être envoyé tel quel au client.

---

## Pipeline en aval

`audit-ux` est la première étape d'un pipeline en trois niveaux :

```
audit-ux                 →    Cadrage stratégique
                               ↓
UI/UX Pro Max            →    Génération de design system
(ou équivalent)                ↓
Vercel Web Interface     →    Revue de code UI
Guidelines (ou équivalent)    
```

`audit-ux` ne remplace pas les outils en aval. Elle les nourrit avec les décisions stratégiques. Un générateur de design system lancé sans cadrage stratégique produit des propositions plausibles mais génériques. La section dédiée du livrable (passation vers la direction artistique) est conçue pour alimenter ces générateurs avec les contraintes issues du cadrage.

---

## Ce qu'il y a dans le repo

```
audit-ux/
├── SKILL.md                              Manifeste principal de la skill
├── assets/
│   └── template-cadrage.md               Template du livrable
└── references/
    ├── questions-par-phase.md            Catalogue de questions par phase
    ├── regles-redactionnelles.md         Sept règles de rigueur
    ├── anti-patterns-universels.md       Anti-patterns universels du web
    ├── fondamentaux-ux.md                Nielsen, Lois UX, Gestalt, accessibilité
    ├── frameworks-conversion.md          Wiebe, Dry, Hormozi, Miller, Cialdini, Schwartz, Heath
    └── frameworks-positionnement.md      Ries & Trout, Dunford, VPC, JTBD, Moore, Godin
```

La skill est construite autour de références modulaires. Le SKILL.md principal est dimensionné pour un chargement rapide. Les références sont chargées à la demande par phase, jamais systématiquement.

---

## Limitations connues

- **Langue** : le contenu interne est en français. Les anglophones peuvent utiliser la skill mais obtiendront des livrables en français. Une traduction anglaise est sur la roadmap.
- **Signature culturelle** : les frameworks marketing tier 2 et tier 3 portent une culture copywriting majoritairement nord-américaine. La skill le signale et invite à filtrer selon le contexte client.
- **Pas un substitut à la recherche utilisateur** : la skill travaille sur la matière que vous lui fournissez. Si vous avez besoin de preuves utilisateurs, conduisez des entretiens séparément.
- **Pas un substitut au conseil stratégique personnel** : la skill encode une méthode, pas votre perspective. Le calibrage initial ou un fichier d'identité adjoint font entrer votre perspective. Sans l'un ou l'autre, la skill produit un cadrage juste mais relativement neutre.
- **Accessibilité traitée en direction structurelle** : pas en audit de conformité formel. Pour un check de conformité légale, commandez un audit dédié séparé.
- **Sortie markdown** : pas de génération directe en Word, Notion ou PDF. La conversion est simple mais manuelle.

---

## Contribuer

Les contributions les plus utiles, par ordre de priorité :

- Aide à la traduction anglaise du SKILL.md, du template, et des références
- Cas de test de profils distincts avec autorisation de publier des post-mortems anonymisés
- Anti-patterns sectoriels à ajouter à la liste universelle, avec justification claire
- Templates de skills d'identité professionnelle comme exemples
- Traductions des notes culturelles pour les contextes non-occidentaux

---

## Note de l'auteur

Cette skill existe parce que j'ai fait les erreurs qu'elle prévient maintenant. J'ai démarré des projets de refonte sans cadrage assez profond, comblé en cours de route avec des suppositions, et livré du travail correct mais pas tranchant. La skill est ce que j'aurais voulu avoir il y a dix ans, encodé pour ne plus avoir à le retenir sous pression.

— Yann
