---
client: <Nom du client>
date_cadrage: <YYYY-MM-DD>
redige_par: <Nom de l'utilisateur>
version: 1.0
voie: <Voie 1 — cadrage complet, matière suffisante> OU <Voie 2 — cadrage hypothétique, matière partielle>
statut: interne — non destiné au client
---

# Cadrage redesign — <Nom du client>

> Ce document est un support de décision interne. Il n'est pas destiné à être transmis au client tel quel. Il sert de socle pour la direction artistique, la production, et le chiffrage qui suivent.

<!--
BLOC VOIE 2 — CONDITIONNEL
À inclure uniquement si le cadrage est produit en Voie 2 (matière insuffisante).
Sinon, supprimer tout ce bloc jusqu'au "---" qui le ferme.
-->

> **⚠️ Avertissement Voie 2 — cadrage hypothétique**
>
> Ce document est produit en **Voie 2** (référence : `regles-redactionnelles.md` et `questions-par-phase.md` Phase 5 Bucket 1). La matière disponible au moment de sa rédaction est partielle :
> - [Cocher / lister ce qui est disponible vs manquant]
> - ✓ Brief client — <préciser l'état : complet / réduit à X / absent>
> - ✓ ou ❌ Analyse existant — <préciser les sources et leurs limites>
> - ✓ ou ❌ Réponses stratégiques du client — <préciser>
> - ✓ ou ❌ Heatmaps / analytics — <préciser>
> - ✓ ou ❌ Analyse concurrence — <préciser>
>
> Les hypothèses structurantes sont formellement marquées dans l'annexe A. Ce cadrage **doit être validé avec le client** avant mise en production. Si les hypothèses sont validées, le cadrage tient. Si elles sont invalidées, tout ou partie est à retravailler.

---

**Contexte du projet** : <2-3 lignes max. Qui est le client, quel est son business, pourquoi un redesign maintenant.>

**Périmètre initial commandé** : <ce qui est inclus dans le redesign tel que commandé par le client.>

**Périmètre recommandé** *(si différent du commandé)* : <extension proposée si le scope commandé est sous-dimensionné, avec référence à la règle 7 d'hygiène rédactionnelle.>

**Posture professionnelle appliquée** : <nom de la skill d'identité chargée, "réponses de calibrage initial", ou "socle neutre" si aucune.>

---

## 1. Verdict stratégique

*Une page maximum. Si ça dépasse une page, c'est que ce n'est pas un verdict, c'est une description.*

### Ce qui cloche aujourd'hui
*3 à 5 points. Formulés en conséquences business, pas en features techniques.*

- …
- …
- …

### Ce qui doit rester
*2 à 3 points. Ce qui fonctionne dans l'existant et qu'il ne faut pas casser.*

- …
- …

### Le pari stratégique
*Une seule phrase. L'angle qu'on assume même si c'est risqué. Cette phrase doit pouvoir être tenue face à un client qui pousse dans une autre direction.*

> …

---

## 2. Persona principal tranché

### Persona principal : <nom court + archétype en une phrase>

*Préciser l'axe de différenciation choisi : B2C / B2B / particulier / professionnel / étudiant / enseignant / donateur / bénévole / utilisateur final / acheteur / etc. — selon ce qui est pertinent pour cette organisation.*

| Attribut | Valeur |
|---|---|
| **Qui** | <Description démographique et situationnelle en une ligne> |
| **Job-to-be-done** | <Le vrai problème qu'il cherche à résoudre, pas l'offre du client> |
| **Douleur principale** | <Ce qui l'empêche d'agir aujourd'hui> |
| **Frein de décision** | <Ce qui bloque la signature, même après conviction> |
| **Preuve qui le rassure** | <Le type de proof qui fait basculer : réalisation, témoignage, certification, chiffre, méthode> |
| **Canal d'arrivée principal** | <SEO / paid / recommandation / prescription> |
| **Segments écartés — pourquoi** | <Les autres segments possibles et pourquoi on les sacrifie dans ce cadrage> |

### Persona secondaire : <nom court + archétype en une phrase> *(si applicable — sinon supprimer cette section)*

*Préciser l'axe de différenciation par rapport au persona principal. Si l'organisation ne sert qu'une cible homogène, supprimer toute cette sous-section.*

| Attribut | Valeur |
|---|---|
| **Qui** | … |
| **Job-to-be-done** | … |
| **Douleur principale** | … |
| **Frein de décision** | … |
| **Preuve qui le rassure** | … |
| **Canal d'arrivée principal** | … |
| **Segments écartés — pourquoi** | … |

---

## 3. Sitemap cible

```
/
├── /page-1
├── /page-2
│   ├── /sous-page-2-1
│   └── /sous-page-2-2
├── /page-3
└── /contact
```

### Notes de sitemap

*Pour chaque page ajoutée, supprimée ou fusionnée par rapport au sitemap actuel : une ligne de justification.*

- **Ajoutée** — `/…` : …
- **Supprimée** — `/…` : …
- **Fusionnée** — `/…` ← `/…` + `/…` : …

---

## 4. Plan de sections

### 4.1 Homepage

*La home a deux rôles : qualifier le visiteur en moins de 5 secondes, et orienter vers le tunnel le plus pertinent pour son profil.*

| # | Section | Objectif | Contenu clé | Contrainte a11y |
|---|---|---|---|---|
| 1 | <nom> | <en une phrase> | <éléments qui doivent y figurer> | <si contrainte structurelle WCAG/EAA> |
| 2 | … | … | … | … |
| … | … | … | … | … |

### 4.2 Page tunnel critique #1 : <nom>

**Pourquoi cette page est critique** : <justification : c'est là que se joue la conversion / la réassurance / la qualification / etc.>

| # | Section | Objectif | Contenu clé | Contrainte a11y |
|---|---|---|---|---|
| 1 | … | … | … | … |

### 4.3 Page tunnel critique #2 : <nom>

**Pourquoi cette page est critique** : …

| # | Section | Objectif | Contenu clé | Contrainte a11y |
|---|---|---|---|---|
| 1 | … | … | … | … |

### 4.4 Page tunnel critique #3 : <nom> *(optionnelle)*

*Inclure uniquement si une 3e page tunnel se justifie vraiment. La parcimonie est un signal de qualité du cadrage.*

| # | Section | Objectif | Contenu clé | Contrainte a11y |
|---|---|---|---|---|
| 1 | … | … | … | … |

---

## 5. Décisions structurelles non négociables

*Entre 3 et 7 décisions. Elles orientent toute la direction artistique qui suit et ne sont pas revisitables sans remettre en cause tout le cadrage.*

1. **<Décision>** — <justification en une phrase, ancrée dans une donnée ou un parti-pris stratégique>
2. **<Décision>** — …
3. **<Décision>** — …

---

## 6. Bugs critiques à corriger avant redesign

*Scoring :*
- *Impact* = effet sur les chiffres de référence ou la qualité des décisions du redesign (**Fort / Moyen / Faible**)
- *Effort* = ressources à mobiliser pour corriger (**Fort / Moyen / Faible**)

| # | Bug | Impact | Effort | Délai recommandé | Justification |
|---|---|---|---|---|---|
| 1 | … | F/M/F | F/M/F | avant démarrage redesign \| en parallèle \| avant mise en prod | <une phrase> |
| 2 | … | … | … | … | … |
| 3 | … | … | … | … | … |

---

## 7. Passation vers la direction artistique

*Cette section distille les contraintes issues du cadrage pour qu'elles soient exploitables par la phase de direction artistique qui suit — qu'elle soit menée manuellement par un directeur artistique ou alimentée par un générateur de design system (type UI/UX Pro Max ou équivalent).*

### 7.1 Contraintes identitaires issues du cadrage

*Ce qui doit impérativement transparaître dans la DA, et pourquoi.*

- **Piliers identitaires à incarner visuellement** : <lister les 2-4 piliers majeurs du client identifiés en phase 4, avec traduction visuelle attendue. Ex : "Ancrage français — à traduire par un vocabulaire visuel éloigné du techno-spatial américain ; privilégier photographie incarnée plutôt qu'illustrations abstraites">
- **Catégorie de marché assumée** : <la catégorie contre laquelle le client se positionne, d'après Dunford. Ex : "Alternative française à Starlink — pas concurrent direct d'Orange/Free sur la fibre">
- **Persona visuel dominant** : <2-3 lignes sur qui on cherche à rassurer/séduire visuellement — souvent plus étroit que le persona business complet>

### 7.2 Contraintes structurelles à respecter

*Ce qui est fixé par le cadrage et ne doit pas être renégocié en DA.*

- **Structure du hero** : <choix du cadrage, ex : "Hero identitaire avec CTA unique test d'éligibilité — pas de double CTA, pas de carrousel">
- **Hiérarchie des sections home** : <renvoyer à la section 4.1 du cadrage>
- **Traitement a11y** : contraste AAA sur éléments critiques, cible ≥ 44x44px, navigation clavier visible, pas de carrousel automatique
- **Largeurs de cible** : mobile-first si le trafic le justifie (préciser), sinon desktop-first responsive

### 7.3 Anti-patterns à exclure

*Ce que la DA ne doit pas produire, même si le client le demande.*

- **Anti-patterns universels retenus** (issus de `anti-patterns-universels.md` et identifiés comme risques sur ce projet) : <lister>
- **Anti-patterns sectoriels** : <si le client opère dans un secteur où certains codes visuels sont disqualifiants — ex : "pas de purple/pink gradient pour un acteur banking, pas de cyber/sci-fi pour un service médical">
- **Anti-patterns identitaires de l'utilisateur** : <si une skill d'identité professionnelle est chargée ou si des réponses de calibrage existent, ses propres exclusions — sinon N/A>

### 7.4 Ce qui reste à trancher en direction artistique

*Ce que le cadrage n'a volontairement pas décidé pour ne pas empiéter sur la DA.*

- Palette précise (le cadrage peut suggérer une direction chromatique, pas une palette finale)
- Typographies précises (le cadrage peut suggérer une personnalité typographique, pas un pairing fermé)
- Style photographique / d'illustration détaillé
- Traitements d'animation / micro-interactions
- Système de grille et espacements

*Un générateur de design system appelé à ce stade doit être nourri des contraintes 7.1 à 7.3 pour produire des propositions cohérentes avec le cadrage — pas lancé à partir d'une description nue du projet.*

---

## Annexes *(optionnelles, à inclure si pertinent)*

### A. Questions restées ouvertes

*Décisions que le client n'a pas tranchées et qu'il faut reposer en rendez-vous de cadrage, OU points que l'utilisateur n'a pas pu trancher seul.*

- …
- …

### B. Sources et documents consultés

- **Brief client** : <référence / date de réception>
- **Heatmaps Clarity** : période <date – date>
- **Analytics** : période <date – date>, source <GA / autre>
- **Concurrents analysés** : <liste des URLs>
- **Posture professionnelle** : <nom de la skill d'identité, "réponses de calibrage initial", ou "socle neutre">
- **Ressources mobilisées** : <tier 1 / tier 2 / tier 3, à cocher selon ce qui a été chargé>

### C. Hors scope explicite

*Pour éviter les malentendus en aval (direction artistique, production, devis), rappeler ce que ce cadrage ne couvre PAS.*

- Direction artistique complète (typographies détaillées, palette finale, moodboard)
- Chiffrage / devis
- Planning projet
- Audit WCAG exhaustif
- Plan de mesure post-redesign (KPIs, events analytics, dashboards)
- Production du livrable client final (proposition commerciale, présentation)
