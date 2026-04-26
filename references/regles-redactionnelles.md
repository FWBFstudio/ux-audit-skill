# Hygiène rédactionnelle du livrable de cadrage

Ce fichier est chargé en Phase 5 au moment de rédiger le livrable. Il cadre les règles qui empêchent un cadrage de dériver vers des affirmations non étayées, des statistiques fabriquées, ou des formulations creuses. Un cadrage qui contient des hallucinations perd sa crédibilité entière — mieux vaut dire moins mais être irréprochable.

---

## Règle 1 — Ne jamais fabriquer de statistiques

Les statistiques précises ("78 % des visiteurs abandonnent après 3 secondes", "selon le MIT, 62 % des utilisateurs...") sont **très coûteuses à reconstruire** si elles sont fausses : elles décrédibilisent tout le reste du document aux yeux du client ou de l'équipe.

### Ce qui est autorisé

- **Invoquer un principe UX établi sans nombre** : *"la vitesse de chargement mobile est un facteur majeur de rebond selon les heuristiques d'ergonomie classiques"*, *"les formulaires longs réduisent les taux de complétion — principe largement documenté"*.
- **Citer une source si et seulement si tu en es certain à 100 %** : nom exact de l'étude, année, chiffre exact. En cas de doute, ne pas citer.
- **Utiliser les données du client lui-même** : *"les heatmaps Clarity montrent que 60 % des visiteurs décrochent avant le fold"* — c'est une donnée de l'audit, pas une stat fabriquée.
- **Formuler en tendance qualitative** : *"la majorité des visiteurs mobile abandonnent rapidement"*, *"une part significative du trafic"*.

### Ce qui est interdit

- Citer un pourcentage précis sans être capable de nommer la source exacte.
- Attribuer une étude à une institution célèbre (MIT, Nielsen Norman Group, Baymard Institute) sans avoir vérifié la citation.
- Reformuler un principe vague en chiffre précis ("en général, la conversion baisse avec les formulaires longs" → *"les formulaires de plus de 5 champs réduisent la conversion de 34 %"*).

---

## Règle 2 — Distinguer fait, observation et hypothèse

Dans un livrable de cadrage, trois niveaux d'assertion coexistent. Il faut les **marquer explicitement** dans la formulation.

| Niveau | Signal verbal | Exemple |
|---|---|---|
| **Fait vérifié** | *"[les analytics montrent / les heatmaps indiquent / le brief mentionne]"* | *"Les analytics montrent 74 % de trafic mobile."* |
| **Observation du crawl** | *"[dans les pages crawlées / à partir des captures fournies]"* | *"Dans les pages crawlées, aucun CTA de prise de contact n'a été trouvé avant le second scroll."* |
| **Hypothèse** | *"[probable / à valider / suppose que]"* | *"Probable : le visiteur arrivant via une requête longue-traîne cherche un devis immédiat — à valider par heatmap de la page d'atterrissage correspondante."* |

Quand l'hypothèse est structurante pour le livrable (persona tranché, pari stratégique), elle doit être **explicitement signalée** dans la section Annexe A "Questions restées ouvertes" du template.

---

## Règle 3 — Absent vs non trouvé

Règle déjà énoncée dans le SKILL.md et en Phase 2/3 de `questions-par-phase.md`. Rappel pour le moment rédactionnel :

- ❌ *"Le site n'a pas de formulaire de contact."* (Affirme une absence sur la base d'un crawl partiel.)
- ✓ *"Formulaire de contact non trouvé dans les pages crawlées — vérification manuelle recommandée."*
- ❌ *"Aucun concurrent n'affiche ses prix."* (Conclusion stratégique sur un constat potentiellement incomplet.)
- ✓ *"Sur les 3 concurrents analysés, aucune page 'pricing' n'apparaît dans les pages crawlées. À confirmer par navigation manuelle avant d'en tirer une conclusion stratégique."*

---

## Règle 4 — Findings : cause, impact, action

Un finding pauvre nomme un symptôme. Un finding utile **explique la cause**, **nomme l'impact business**, **propose une action**.

### Exemple — bouton peu visible

❌ *"Le bouton 'Demander un devis' est peu visible."*

✓ *"Le bouton 'Demander un devis' a un contraste faible avec le fond de page (blanc sur beige clair). Les éléments de conversion gagnent à respecter un ratio de contraste d'au moins 4.5:1 (recommandation WCAG AA) — au-delà de l'enjeu d'accessibilité, un CTA qui fond dans le fond n'est pas identifié comme interactif. **Action** : passer le bouton sur fond bleu foncé avec texte blanc, ou ajouter une bordure contrastée. **Note** : le contraste exact n'a pas été mesuré — à vérifier en phase de direction artistique."*

### Exemple — formulaire long

❌ *"Le formulaire de contact est trop long."*

✓ *"Le formulaire de contact demande 9 champs dont 4 optionnels. Pour un premier contact, la pratique établie est de se limiter à 3–5 champs essentiels — ici nom, email, téléphone, projet suffisent. Les autres (budget, surface, délai souhaité, mode de contact préféré, commentaire libre) peuvent être déplacés en étape 2 après prise de contact, ou en sous-champs repliés. **Action** : refondre le formulaire en deux étapes, avec l'étape 1 limitée à 4 champs."*

### Exemple — proposition de valeur vague

❌ *"La proposition de valeur de la home manque de clarté."*

✓ *"La proposition de valeur en hero ('Votre partenaire de confiance depuis 1998') ne différencie pas le client de ses concurrents — la même promesse figure chez 2 des 3 concurrents analysés. Pour un persona en phase d'évaluation active, cette formule ne fournit aucun critère de choix. **Action** : remplacer par une promesse qui combine le job-to-be-done du persona + le différenciateur concret du client (ex : méthode propriétaire, zone d'intervention exclusive, garantie spécifique)."*

---

## Règle 5 — Le scoring impact × effort doit être défendable

Le scoring Fort/Moyen/Faible × Fort/Moyen/Faible n'est pas un gadget. Il sert à construire le devis et à prioriser l'exécution. Un scoring gonflé le vide de sa valeur.

**Barème de calibration** :

### Impact

- **Fort** : le bug fausse les données de référence OU bloque une conversion OU décrédibilise visiblement le site auprès du persona cible.
- **Moyen** : le bug crée une friction mesurable mais n'empêche pas la conversion ; dégrade la perception sans être disqualifiant.
- **Faible** : le bug est de l'ordre du détail de finition, visible seulement à l'examen attentif.

### Effort

- **Fort** : nécessite un développement structurel (refonte d'un composant, migration, changement de stack), ou une décision client non triviale.
- **Moyen** : correction localisée qui demande du temps d'intégration mais pas de décision structurante.
- **Faible** : quick win, correction de texte, ajustement CSS mineur.

**Règle d'hygiène** : avant d'assigner "Fort" en impact, se demander si le bug est vraiment de ce niveau, ou si on se laisse emporter par l'emphase. Un document où la moitié des bugs sont "Impact Fort / Effort Faible" révèle soit un site catastrophique, soit un scoring inflaté.

---

## Règle 6 — Adapter au contexte sectoriel avant de conclure

Une heuristique UX n'est pas une loi universelle. Avant de conclure qu'un élément est un problème, vérifier qu'il l'est **dans le contexte sectoriel du client**.

Exemples de rappel :

- **Éléments d'urgence** (*"plus que 3 places !"*, compte à rebours) : efficaces en e-commerce et en billetterie, souvent manipulateurs et contre-productifs sur le site d'un avocat, d'un médecin, d'un cabinet d'architectes.
- **Affichage des prix** : critique dans la plupart des contextes professionnels où la dissimulation est un frein, souvent volontairement absent dans le luxe ou le sur-mesure où le prix fait partie de la qualification.
- **Témoignages vidéo** : très puissants en formation et coaching, parfois dissonants dans un contexte industriel où les études de cas écrites portent plus.
- **Chatbot** : pertinent pour des services à volume, souvent une charge perçue dans un contexte artisanal où la relation humaine est la promesse.

**Question à se poser systématiquement** : *"Est-ce un problème dans ce secteur, pour ce persona, à ce moment du tunnel ?"* Si la réponse n'est pas évidente, marquer le finding comme "à arbitrer" plutôt que comme critique.

---

## Règle 7 — Détecter et signaler un scope sous-dimensionné

Le client demande parfois un cadrage sur un périmètre qui **ne correspond pas au parcours utilisateur logique**. Cas fréquents :

- *"Refonte de la home seule"* alors que la conversion se joue dans le tunnel qui suit (exemple typique : un opérateur télécoms dont la home est un entonnoir vers un test d'éligibilité).
- *"Refonte de la page contact uniquement"* alors que la friction est en amont (les visiteurs n'arrivent pas jusque-là).
- *"Refonte du tunnel e-commerce"* alors que le problème est le trafic entrant (on optimise ce qui convertit déjà bien avec un trafic trop faible).
- *"Refonte de la landing page X"* isolée de l'écosystème qui la nourrit (SEO, campagnes, email).

La skill doit **détecter** ces cas en confrontant le scope commandé à la logique de parcours observée dans la Phase 2, et les **signaler explicitement** à l'utilisateur.

### Formulation type à destination de l'utilisateur

Quand le scope commandé semble sous-dimensionné :

> *"Le scope commandé est [X]. En observant [Y dans la matière disponible], je constate que la conversion réelle se joue dans [Z] qui est hors scope. Refaire [X] sans intervenir sur [Z] plafonne structurellement l'impact du redesign. Je recommande d'étendre le scope à [X + Z]. Si ce n'est pas possible (budget, politique interne), il faut l'accepter et documenter explicitement la limitation dans le livrable et dans le chiffrage."*

### Traitement dans le livrable

Quand l'utilisateur confirme qu'il reste sur le scope commandé malgré le signal :

- **Verdict stratégique** : mentionner explicitement la recommandation d'extension de scope (que le client pourra accepter ou refuser en rendez-vous).
- **Annexe A (Questions restées ouvertes)** : faire figurer la question de l'extension de scope comme point à valider avec le client.
- **Hors scope explicite** : rappeler en annexe C ce qui est exclu et pourquoi c'est une limite du cadrage, pas un choix technique.

### Pourquoi c'est critique

Un cadrage qui accepte aveuglément un scope restrictif sans le signaler fait porter la responsabilité de l'échec sur le professionnel qui a livré le cadrage (*"le redesign n'a pas marché, vous êtes nuls"*) plutôt que sur le scope initial (*"on vous avait prévenu, le périmètre était insuffisant"*). **Documenter la limite est une protection commerciale autant qu'une rigueur intellectuelle.**
