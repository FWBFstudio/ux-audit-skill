# Questions canoniques par phase du cadrage

Ce fichier est la banque des questions que la skill mobilise pour accompagner l'utilisateur pendant un cadrage de redesign. Il n'est **pas une checklist à dérouler intégralement** — c'est un répertoire dans lequel la skill pioche selon la matière déjà fournie, la phase en cours, et les signaux détectés dans la conversation.

## Comment utiliser ce fichier

- **Ne jamais poser toutes les questions d'une phase d'un coup.** Trop de questions en bloc saturent l'utilisateur et diluent les vraies décisions. Piocher par groupes de 2-4 questions maximum par tour.
- **Adapter les formulations** au ton de la conversation. Les questions ci-dessous sont des prototypes, pas des scripts.
- **Distinguer deux types de destinataires** :
  - **À l'utilisateur directement** — questions que Claude pose à la personne qui conduit le cadrage (le professionnel — designer, studio, freelance, consultant, designer interne).
  - **Au client via l'utilisateur** — questions que l'utilisateur doit faire remonter au client final, et dont les réponses reviendront dans une phase ultérieure.
- **Si une réponse est déjà implicite dans la matière fournie** (brief, captures, etc.), ne pas la reposer.

---

## Phase 1 — Intake

Objectif : comprendre le business, le contexte, les attentes déclarées du client, la vraie nature du brief.

### À l'utilisateur sur le client

- Qui t'a contacté ? Le décideur final, un intermédiaire, un service marketing ? *(Ça change tout sur le temps d'itération à prévoir.)*
- Comment le prospect est-il arrivé à toi ? Recommandation, approche sortante, appel d'offres ? *(Ça conditionne son niveau d'engagement.)*
- Quel est le budget approximatif évoqué, même en fourchette floue ? Et quelle est sa marge d'élasticité ?
- Qu'est-ce qui a déclenché le besoin de refonte **maintenant** ? Obsolescence visuelle, baisse de leads, concurrent qui avance, changement d'offre, contrainte légale type EAA ?
- Le client a-t-il déjà un prestataire en place ? Si oui, pourquoi il change ?

### À l'utilisateur sur le brief fourni

- Le brief est-il écrit ou oral ? Qui l'a rédigé ?
- Qu'est-ce qui, dans ce brief, est une **demande** du client versus qu'est-ce qui est déjà une **solution** qu'il a décidée unilatéralement ? *(Distinction clé : les solutions pré-décidées sont souvent ce qu'il faut challenger en premier.)*
- Qu'est-ce qui manque dans ce brief que tu attendrais normalement ? Objectifs chiffrés, KPIs, cible précise, contraintes techniques ?

### Au client, via l'utilisateur

- Quel est l'objectif business chiffré de la refonte sur 12 mois ? *(Leads, CA, trafic, autre.)*
- Quel est le tunnel de conversion actuel, même approximativement ? *(Du visiteur à la facture signée.)*
- Quels sont les 3 concurrents que **le client cite spontanément** ? *(Souvent différents des concurrents réels du marché — révélateur de sa perception.)*
- Qu'est-ce que le client ne veut **surtout pas** pour son nouveau site ? *(Les repoussoirs sont plus informatifs que les inspirations.)*

---

## Phase 2 — Analyse existant

Objectif : diagnostiquer l'existant (bugs critiques, frictions, comportements réels) à partir des captures, heatmaps si disponibles, analytics si disponibles, et check-up technique.

**Cas nominal : sans heatmaps.** Dans la pratique, la plupart des clients ne fournissent pas de heatmaps (Clarity ou équivalent), et il ne faut pas les attendre. La Phase 2 doit produire un diagnostic valable **sans** cette donnée, en s'appuyant sur : captures d'écran, analyse manuelle des parcours, règles objectives (Nielsen, Lois UX, Krug, anti-patterns universels), analytics si disponibles, et substituts comportementaux (retours SAV, questions récurrentes des clients, comparaison avec concurrents). Les heatmaps, quand elles existent, sont un **enrichissement** qui affine le diagnostic — pas un prérequis.

**Règle critique applicable à toute cette phase** : distinguer ce qui est **absent du site** de ce qui est **non trouvé dans le crawl ou les captures**. Ne jamais affirmer "le site n'a pas X" sur la base d'un fetch partiel ou de captures incomplètes. Écrire systématiquement "X non trouvé dans les données disponibles — vérification manuelle recommandée" quand il y a un doute raisonnable.

### Bucket 1 — À l'utilisateur sur la qualité des inputs

*Souvent oublié, mais détermine la fiabilité du diag qui suit.*

- As-tu les captures des pages clés en version **desktop ET mobile** ? *(Un diag mobile-only biaise le verdict pour certaines cibles — typiquement professionnelles ou seniors qui consultent davantage en desktop ; un diag desktop-only est disqualifiant aujourd'hui pour la plupart des cibles grand public.)*
- As-tu un accès direct à Clarity ou des exports/captures fournis par le client ? *(L'accès direct permet de filtrer par segment, les exports non.)*
- Quelle période couvrent les analytics que tu as ? *(Moins de 3 mois = tendances peu fiables ; une seule saison = risque de biais saisonnier.)*
- Y a-t-il eu un événement majeur sur la période couverte — campagne Ads, pic saisonnier, bug technique, relance d'offre ? *(Ça fausse tout le reste.)*

### Bucket 2 — Lecture des heatmaps Clarity *(si disponibles)*

À mobiliser uniquement quand l'utilisateur fournit des heatmaps. Si ce n'est pas le cas, passer directement au Bucket 2bis.

- **Attention** : où les utilisateurs s'attardent-ils vraiment ? Est-ce cohérent avec les objectifs business du client, ou ils s'attardent sur des zones décoratives ?
- **Scroll** : à quelle hauteur de page 50 % des visiteurs décrochent-ils ? Le contenu clé (proposition de valeur, CTA principal, preuve sociale) est-il au-dessus ou en-dessous de ce seuil ?
- **Tap** : les utilisateurs tapent-ils sur des éléments **non cliquables** ? *(Signal fort de malentendu UX : ils ont pris une image pour un bouton, un titre pour un lien.)*
- **Rage clicks** : y a-t-il des zones de clics répétés sur un même élément ? *(Indicateur de frustration, souvent un bouton qui ne répond pas ou un lien cassé.)*

### Bucket 2bis — Substituts comportementaux quand heatmaps indisponibles

*Cas nominal en pratique. Ces substituts sont parfois plus précieux qu'une heatmap parce qu'ils révèlent les incompréhensions explicites plutôt que des zones de chaleur interprétables.*

- Le client a-t-il un **service client / SAV** qui reçoit des questions récurrentes ? Les 10-15 questions les plus fréquentes **révèlent** ce que le site ne dit pas clairement. *(Exemple : si le SAV reçoit tous les jours "quels sont vos délais ?", c'est que l'information n'est pas lisible sur le site — même sans heatmap.)*
- Peux-tu obtenir les **5-10 derniers mails types** que le client reçoit de prospects ? *(Ils révèlent les frictions réelles : objections, demandes de renseignement sur des points qui devraient être évidents.)*
- Le client a-t-il un **chat ou chatbot** dont les logs sont accessibles ? *(Même anonymisés, les échanges révèlent les blocages utilisateur.)*
- **Test utilisateur minimal** : l'utilisateur peut-il faire tester la home par 2-3 personnes de son entourage (non techniciens) en mode *"trouve comment obtenir un devis"* ou *"trouve ce que fait cette entreprise"* ? Même informel, ça révèle énormément.
- **Lecture manuelle scrupuleuse des parcours** : parcourir soi-même le site comme un visiteur naïf, en notant chaque point où on hésite, chaque décision ambiguë. La discipline compense en partie l'absence de données comportementales.

### Bucket 3 — Lecture des analytics *(si disponibles)*

À mobiliser quand l'utilisateur fournit un accès ou des captures analytics. Souvent partiellement disponibles même quand les heatmaps ne le sont pas.

- Quelle est la **source de trafic principale** ? SEO organique, paid, direct, social, referral ? *(Ça conditionne la lecture de tout le reste — un trafic SEO et un trafic paid se comportent différemment.)*
- Quelle est la **page d'entrée la plus fréquente** ? La home ou une page profonde ? *(Si ce n'est pas la home, le cadrage du hero doit en tenir compte.)*
- Quel est le **taux de rebond des pages tunnels** critiques (contact, devis, formulaire) ?
- Y a-t-il un **écart massif desktop vs mobile** en taux de conversion ? *(Si oui, le redesign doit être pensé mobile-first même si le trafic est majoritairement desktop.)*

### Bucket 4 — Diagnostic technique à mener soi-même

- Temps de chargement mobile en 4G ? *(Test rapide via PageSpeed Insights ou WebPageTest. Au-dessus de 3s, c'est un bug critique.)*
- Erreurs console visibles en navigation normale ? *(Indicateur d'hygiène tech, et futur casse-tête pour la migration.)*
- Les formulaires fonctionnent-ils réellement ? *(Test à la main — envoyer un faux lead.)*
- Liens internes cassés, HTTPS correctement déployé, mentions légales et politique de cookies à jour ?

### Bucket 5 — Synthèse diagnostic

*Déclenche la transition vers les phases suivantes.*

- Parmi tous ces constats, quels sont les **3 bugs qui doivent être corrigés AVANT le redesign** — parce qu'ils faussent les chiffres de référence ou parce qu'ils plombent l'existant au point de biaiser les décisions qu'on va prendre ?
- Y a-t-il un écart manifeste entre ce que **dit le client** dans son brief et ce que **montrent les données** ? *(Si oui, c'est un point d'entrée pour la phase 4 stratégique.)*

---

## Phase 3 — Analyse concurrence

Objectif : identifier les codes du secteur, les opportunités de différenciation, les anti-exemples.

**Règle critique applicable à toute cette phase** : la règle "absent vs non trouvé" s'applique aussi ici. Un concurrent peut sembler ne pas avoir de page "pricing" simplement parce que le crawl n'est pas allé la chercher. Avant d'en tirer une conclusion stratégique (ex : "aucun concurrent n'affiche ses prix, donc l'affichage des prix est une opportunité"), vérifier manuellement.

### Bucket 1 — Cadrage de la liste de concurrents

*La liste fournie par le client est souvent biaisée : concurrents d'image vs concurrents commerciaux réels.*

- Les 2-3 concurrents listés par le client sont-ils vraiment ses concurrents ? Ou sa perception est-elle biaisée ?
- Qui sont les **concurrents réels** d'après ton analyse, que le client ne nomme pas ? *(Gros acteurs nationaux même s'ils ne sont pas locaux ; alternatives non-évidentes comme le DIY, la grande surface, la solution substitut.)*
- Y a-t-il un **acteur disruptif** dans le secteur — marketplace, modèle alternatif, pure player — qui pourrait rebattre les cartes même s'il n'est pas cité par le client ?

### Bucket 2 — Codes visuels et éditoriaux du secteur

- Quelles sont les 2-3 **typologies visuelles dominantes** dans le secteur ? *(Exemples possibles selon les secteurs : chez les artisans, photos de chantier + texte technique + formulaire vs photos de belle maison + témoignages vs minimaliste type architecte ; en SaaS, dashboards colorés + features list vs hero vidéo + logos clients vs landing éditoriale ; dans la restauration, photos de plats close-up vs ambiance lifestyle vs chef-centric.)*
- Quels sont les **tropes copy récurrents** ? *(Promesses creuses type "qualité, savoir-faire, sur-mesure" chez les artisans ; positionnements standardisés en SaaS.)*
- Quel est le **niveau de sophistication** moyen du secteur — amateur, pro solide, premium ? *(Ça conditionne où se positionner : remonter d'un cran suffit souvent à se détacher.)*

### Bucket 3 — Opportunités de différenciation

- Quelle case **personne n'occupe** dans le paysage concurrentiel observé ?
- Quelle case **plusieurs concurrents occupent mal** — une promesse qu'ils font tous mais qu'aucun ne démontre ?
- Quels **formats de page** sont sous-exploités dans le secteur ? *(Études de cas détaillées, configurateur, calculateur, guide pédagogique, contenu éditorial.)*

### Bucket 4 — Anti-exemples et synthèse

- Quels sont les 2-3 choix faits par les concurrents qu'il faut **expressément éviter** dans le redesign, et pourquoi ?
- Y a-t-il un **code gagnant du secteur** qu'il faut au contraire reprendre — par conformité au genre — pour ne pas dérouter la cible ? *(Un site d'artisan sans photos de réalisations, un SaaS sans grille tarifaire visible, un restaurant sans menu accessible : tous vont dérouter leur cible même si l'exécution visuelle est plus propre que celle des concurrents.)*
- Dans la liste des pages que tes concurrents proposent, lesquelles sont **toujours présentes** et lesquelles sont **optionnelles** ? *(Ça oriente le sitemap cible de la phase 5.)*
- Si tu devais résumer en une phrase **l'angle que le client peut occuper** que personne d'autre n'occupe, ce serait quoi ? *(C'est la question qui tranche la phase.)*

---

## Phase 4 — Questions stratégiques

Objectif : trancher le positionnement, le persona principal, l'angle éditorial. C'est la phase qui tranche — les autres préparent la matière, celle-ci fait émerger les décisions.

### Bucket 1 — Cadrage commercial et géographique

- Quelle est la **zone de chalandise réelle** du client ? Comment l'as-tu vérifiée au-delà du déclaratif — y a-t-il des zones sur-représentées dans ses clients actuels ?
- Quel est le **mix des cibles servies** dans le CA actuel ? Et dans les **leads** entrants ? *(Souvent très différent — révélateur de ce qu'il faut prioriser sur le site. Les axes de différenciation classiques : B2C/B2B, particulier/professionnel, individuel/institutionnel, court terme/long terme — adapter à la réalité du business.)*
- Quelle part du business vient de la **rétention** vs l'acquisition ? Un site web est-il vraiment un levier d'acquisition pour ce client, ou juste un outil de réassurance ?
- Quelle **saisonnalité** structure le business ? Y a-t-il des pics qui imposent des contraintes sur le timing du redesign ou sur les pages à optimiser en priorité ?

### Bucket 2 — Objectifs et KPIs

- Quel est l'**objectif chiffré à 12 mois**, exprimé en métrique business (pas en "trafic") ? Leads qualifiés, CA, marge ?
- Quel est le **volume actuel des leads** reçus via le site, et combien se transforment en vente ? Le client le sait-il seulement ?
- Y a-t-il un **CRM ou un système de tracking** des leads côté client ? *(Si non, la mesure post-redesign sera approximative et il faut le signaler maintenant.)*
- Quelle est la **valeur vie client moyenne (LTV)** ? *(Détermine combien on peut "investir" pour acquérir un lead, et donc combien le client peut investir dans un site performant.)*

### Bucket 3 — Persona à trancher

- Si tu devais ne retenir qu'**un seul persona principal**, ce serait qui ? *(Forcer le choix — pas trois personas, pas d'hésitation. L'axe de différenciation peut être B2C/B2B, particulier/professionnel, ou tout autre axe pertinent au business.)*
- Si l'organisation sert deux cibles structurellement distinctes (ex : utilisateur final + acheteur, donateur + bénévole, étudiant + enseignant), faire le même exercice pour le persona secondaire — un seul.
- Pour le persona principal retenu : quel est son **job-to-be-done** — le vrai problème qu'il cherche à résoudre, pas juste "acheter l'offre du client" ?
- Qu'est-ce qui **empêche aujourd'hui** ce persona de signer avec le client après avoir visité son site ? *(Sa douleur + son frein de décision.)*

### Bucket 4 — Positionnement et différenciation

*Mobilise Dunford (Obviously Awesome) et le Value Proposition Canvas (Strategyzer).*

- En une phrase : **pour qui** (le persona), **qui fait quoi** (besoin), **notre client est le seul qui** (différenciation), **parce que** (preuve) ?
- Quelles sont les 3 **preuves tangibles** que le client peut mettre en avant sur son site pour soutenir ce positionnement ? *(Réalisations, certifications, chiffres, témoignages, méthode propriétaire.)*
- Dans la proposition de valeur actuelle du client, qu'est-ce qui est **générique** (vrai pour tous les concurrents) et qu'est-ce qui est **spécifique** ? *(L'objectif du redesign : amplifier le spécifique, virer le générique.)*

### Bucket 5 — Angle éditorial et ton

- Quel est le **niveau de maturité** du persona sur le sujet ? *(Novice absolu, averti, expert. Change complètement le ton et la pédagogie nécessaire.)*
- Le site doit-il être d'abord **rassurant**, **expert**, ou **surprenant** ? *(Les trois ne coexistent pas bien — forcer le choix dominant.)*

---

## Phase 5 — Synthèse

Cette phase est différente des autres. Elle ne collecte plus d'inputs, elle **tranche et synthétise**. Le vrai contenu de la Phase 5 — la logique de construction de chaque section du livrable — vit dans `assets/template-cadrage.md`. Dans ce fichier-ci, la Phase 5 sert uniquement d'**aiguillage** : check que tout est prêt, et remontée de clarifications si ambiguïté.

### Bucket 1 — Check de complétude avant de basculer + choix de voie

La skill produit ses livrables selon deux voies, à trancher **avant** de démarrer la rédaction. Le choix de voie conditionne la forme du livrable.

**Voie 1 — cadrage complet, matière suffisante**

Conditions cumulatives pour pouvoir s'engager en Voie 1 :
- Brief client consolidé (même oral, mais consolidé par au moins un échange direct avec le décideur).
- Diagnostic existant appuyé sur des captures + analytics + idéalement heatmaps (ou substituts comportementaux solides type retours SAV, test utilisateur minimal).
- Réponses stratégiques du client sur zone de chalandise, mix des cibles servies (au moins ordre de grandeur), objectifs 12 mois.
- Analyse concurrence effectuée sur au moins 2 concurrents cités par le client ou identifiés par l'utilisateur.

Le livrable Voie 1 produit des décisions **fermes**, défendables face au client sans réserve. Les hypothèses ouvertes sont marginales et documentées en annexe.

**Voie 2 — cadrage hypothétique, matière insuffisante**

Conditions de déclenchement (au moins une) :
- Brief client réduit à une ou deux phrases (cas fréquent en pratique : le client ne sait pas formaliser).
- Données comportementales et analytics absentes ou très partielles.
- Réponses stratégiques du client non obtenues malgré relance.
- Décideur non identifié ou inaccessible pendant la phase de cadrage.

Le livrable Voie 2 produit des **propositions** avec hypothèses structurantes explicitement marquées (H1, H2, etc.). Chaque hypothèse est à valider avec le client avant mise en production. Le livrable signale en tête qu'il est conditionnel.

**Règle de bascule** : par défaut, tenter Voie 1. Si l'utilisateur confirme explicitement qu'une des conditions de déclenchement Voie 2 est remplie et non résolvable dans un délai raisonnable, basculer en Voie 2.

**Règle de transparence** : quel que soit le choix de voie, le livrable doit **nommer la voie utilisée en tête de document** (comme le prévoit l'avertissement conditionnel dans `template-cadrage.md`). Le client ne peut pas évaluer la fiabilité du cadrage sans connaître la voie.

### Bucket 1bis — Check de complétude stricte

Avant de basculer en synthèse (Voie 1 ou Voie 2) :

- A-t-on au minimum : brief (même réduit), diagnostic existant (captures + au moins un substitut comportemental), éléments d'analyse concurrence ?
- Y a-t-il des **contradictions non résolues** entre ces éléments qu'il faut lever AVANT de rédiger le livrable ? *(Exemple classique : le brief dit "cible premium", les analytics montrent un trafic bas de gamme.)* Ces contradictions doivent soit être tranchées maintenant (avec remontée à l'utilisateur), soit être marquées comme hypothèses structurantes en Voie 2.
- L'utilisateur est-il explicitement prêt à basculer en synthèse ? *(Ne jamais démarrer la synthèse sans accord explicite — l'utilisateur peut vouloir une nouvelle itération sur la phase 2 ou 4 avant.)*

**Self-check obligatoire avant de rédiger le livrable** — pour chaque finding ou recommandation qu'on va inscrire, se poser trois questions :

1. *Est-ce un fait issu d'une donnée vérifiée, ou une hypothèse que je confonds avec un fait ?* *(Si hypothèse : soit la valider en posant une question à l'utilisateur, soit la signaler explicitement comme hypothèse dans le livrable.)*
2. *Si j'invoque une statistique (ex : "78 % des visiteurs mobile abandonnent après 3 secondes"), suis-je certain de la source exacte et du chiffre exact ?* *(Si non : reformuler sans chiffre précis — "la majorité des visiteurs mobile abandonnent rapidement au-delà de 3 secondes" — ou invoquer un principe UX établi sans nombre.)*
3. *Le niveau de criticité que je donne à ce bug (Fort/Moyen/Faible) est-il justifié par un raisonnement business, ou je l'inflates par habitude ?* *(Un scoring systématiquement gonflé au "Fort" vide le scoring de son utilité.)*

Charger `references/regles-redactionnelles.md` à ce stade pour les règles détaillées et les exemples bad/good.

### Bucket 2 — Questions de clarification à remonter à l'utilisateur si ambiguïté

En rédigeant le livrable, Claude peut se heurter à une décision impossible à trancher seul. Il doit alors **interrompre la rédaction** et remonter la question. Quelques archétypes de conflit :

- **Conflit brief vs données** : *"Tu m'as dit 'cible premium' mais les analytics montrent un trafic bas de gamme. Je tranche pour quoi — le premium (en assumant qu'il faut changer l'acquisition derrière) ou le trafic réel ?"*
- **Conflit focus vs flou sur le persona** : *"La phase 4 a retenu un seul persona principal tranché. Mais il existe au moins deux segments actifs dans la clientèle actuelle du client. On assume de couper un segment dans le redesign (stratégie de focus) ou on élargit au prix d'un persona plus flou ?"*
- **Conflit bug critique vs scope** : *"Tu as identifié 3 bugs critiques en phase 2. Le premier demande un refactor majeur — on l'inclut dans le scope du redesign ou on le traite en amont comme chantier séparé ?"*
- **Conflit données vs stratégie** : *"Les réponses stratégiques du client sur le mix des cibles servies sont incohérentes avec ce que montrent les heatmaps. Je m'aligne sur quoi ?"*
- **Conflit différenciation vs conformité** : *"Aucun des 3 concurrents analysés n'a la page [X] que le client demande dans son brief. Je la garde au sitemap (pari de différenciation) ou je la retire (conformité au genre) ?"*

Ces archétypes illustrent les types de conflits qui peuvent émerger — à Claude de formuler la clarification adaptée au cas réel.
