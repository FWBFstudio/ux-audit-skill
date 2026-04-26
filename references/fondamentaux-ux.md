# Tier 1 — Fondements UX et accessibilité

Ce fichier rassemble les fondamentaux ergonomiques, cognitifs et légaux sur lesquels la skill s'appuie pour diagnostiquer l'existant (phase 2) et justifier les décisions structurelles (phase 5). Il n'est **pas** une checklist à dérouler intégralement — Claude pioche ce qui est pertinent pour le cas rencontré.

---

## 10 heuristiques de Jakob Nielsen

Les heuristiques de Nielsen (formulées en 1994, revues depuis) sont le socle d'évaluation ergonomique le plus utilisé au monde. Chacune est un critère d'inspection — on vérifie si l'interface y répond.

### 1. Visibilité de l'état du système
L'utilisateur doit toujours savoir où il en est. *Exemple de manquement : un bouton qui a été cliqué sans retour visuel, un chargement sans indicateur.*

### 2. Correspondance entre le système et le monde réel
Parler la langue de l'utilisateur, utiliser ses concepts, pas le jargon métier. *Exemple de manquement : "Soumettre le formulaire d'intention d'achat" au lieu de "Demander un devis".*

### 3. Contrôle et liberté pour l'utilisateur
Permettre de revenir en arrière, d'annuler, de quitter un tunnel. *Exemple de manquement : un tunnel de conversion qui piège, sans possibilité de revenir à l'étape précédente sans tout perdre.*

### 4. Cohérence et standards
Faire comme le reste du web. Un lien est bleu et souligné si on est dans l'habitude. Les boutons ressemblent à des boutons. *Exemple de manquement : une navigation principale placée à un endroit inhabituel sans raison stratégique.*

### 5. Prévention des erreurs
Mieux qu'un bon message d'erreur : un design qui rend l'erreur impossible. *Exemple : formulaires qui n'autorisent pas la saisie d'un format de date incorrect.*

### 6. Reconnaître plutôt que se rappeler
Montrer les options plutôt que forcer l'utilisateur à les mémoriser. *Exemple de manquement : un menu qui n'indique pas la page courante.*

### 7. Flexibilité et efficacité d'utilisation
Accélérateurs pour les utilisateurs expérimentés, simplicité pour les novices. *Exemple : raccourcis clavier, recherche, filtres.*

### 8. Esthétique et design minimaliste
Ne pas noyer l'information importante dans du bruit décoratif. *Exemple de manquement : une home avec 15 sections, aucune hiérarchisée.*

### 9. Aider à reconnaître, diagnostiquer et corriger les erreurs
Messages d'erreur qui disent **ce qui ne va pas** et **comment corriger**, pas des codes abstraits. *Exemple de manquement : "Erreur 422 — unprocessable entity".*

### 10. Aide et documentation
Quand la documentation est nécessaire, elle doit être contextuelle, scannable, centrée sur la tâche. *Exemple : info-bulles, tooltips, pages d'aide ciblées.*

### Quand mobiliser Nielsen en cadrage

- En phase 2, comme grille de lecture pour évaluer les captures et les comportements heatmap.
- En phase 5, pour justifier un bug critique ou une décision structurelle.
- **Pas de checklist exhaustive à produire** : on pioche les 3-5 heuristiques les plus violées par l'existant, on en fait des findings actionnables.

---

## Lois de l'UX (Jon Yablonski, lawsofux.com)

Jon Yablonski a compilé les lois cognitives et comportementales qui sous-tendent les décisions d'interface. Les plus structurantes en cadrage de redesign :

### Loi de Fitts
Le temps pour atteindre une cible est fonction de sa distance et de sa taille. *Implications concrètes : les CTA principaux doivent être gros et accessibles (pouce sur mobile, coin supérieur droit ou centre sur desktop). Les zones de clic doivent dépasser visuellement la dimension du texte.*

### Loi de Hick
Le temps de décision augmente avec le nombre de choix. *Implications : réduire le nombre d'options dans un menu principal, hiérarchiser les CTA (un principal, un secondaire, jamais trois au même niveau).*

### Loi de Jakob
Les utilisateurs passent la majorité de leur temps sur d'autres sites. Ils s'attendent donc à ce que votre site se comporte comme ceux qu'ils connaissent. *Implications : ne pas réinventer la navigation, le placement du logo, le panier e-commerce, sauf raison stratégique très forte.*

### Loi de Miller
La mémoire de travail gère environ 7 éléments (±2). *Implications : ne pas imposer de mémoriser plus de quelques éléments à travers un tunnel. Grouper, chunker.*

### Loi de Pareto (80/20)
Environ 80 % des effets viennent de 20 % des causes. *Implications en cadrage : identifier les 2-3 pages et les 3-5 sections qui produisent l'essentiel de la conversion, concentrer l'effort dessus.*

### Loi de Proximité
Les éléments proches les uns des autres sont perçus comme liés. *Implications : regrouper visuellement ce qui appartient au même concept (titre + visuel + CTA d'une même offre), séparer ce qui n'a pas de lien.*

### Loi de l'uniformité / effet von Restorff
Un élément qui sort du lot visuellement est retenu. *Implications : un seul CTA principal par page, typographiquement distinct. Si tout est emphase, rien n'est emphase.*

### Quand mobiliser les Lois UX en cadrage

- En phase 2, pour lire les heatmaps Tap (loi de Fitts) et Scroll (loi de Pareto).
- En phase 5, pour justifier un plan de sections (loi de Proximité, loi de Miller) ou la structure d'un menu (loi de Hick).

---

## Principes Gestalt — la perception visuelle qui structure une page

La théorie de la Gestalt (Wertheimer, Köhler, Koffka, années 1920) décrit comment l'œil humain organise spontanément les éléments visuels en groupes cohérents. C'est la grammaire perceptive sur laquelle tout layout s'appuie, qu'on en ait conscience ou non. Cinq principes structurants en cadrage web :

### Proximité

Les éléments proches sont perçus comme appartenant au même groupe. *Implication : un bloc titre + visuel + CTA doit être visuellement serré pour que l'œil le lise comme une unité. Si le CTA est séparé visuellement de son titre, le lien narratif se perd.*

### Similarité

Les éléments qui se ressemblent (couleur, forme, taille, typographie) sont perçus comme liés. *Implication : tous les CTA primaires doivent partager les mêmes attributs visuels. Mélanger des CTA primaires ronds/orange avec des CTA primaires rectangulaires/bleus rompt la cohérence et génère de l'hésitation.*

### Continuité

L'œil suit naturellement les lignes et trajectoires. Les éléments alignés sur une trajectoire (verticale, horizontale, diagonale) sont perçus comme reliés. *Implication : un alignement de gauche solide rend une page scannable. Un layout qui rompt arbitrairement les alignements force le lecteur à rechercher chaque nouveau bloc.*

### Fermeture

L'œil complète mentalement les formes incomplètes. *Implication : on n'a pas besoin de border tous les blocs pour qu'ils soient perçus comme distincts. Un espacement suffisant + une indication visuelle légère suffisent. L'over-bordering est un signe de manque de confiance dans le rythme typographique.*

### Figure-fond

L'œil distingue automatiquement ce qui est au premier plan de ce qui est au fond. *Implication : le contraste figure/fond doit être net pour le contenu critique. Un texte sur image avec contraste insuffisant viole simultanément la Gestalt et le WCAG.*

### Quand mobiliser Gestalt en cadrage

- Phase 2, pour diagnostiquer pourquoi une page est confuse même quand son contenu est juste : souvent un problème de proximité ou de similarité mal gérée.
- Phase 5, pour justifier les regroupements de sections et les choix d'alignement dans le plan de sections.
- Particulièrement utile pour expliquer à un client non-designer pourquoi son site actuel est *"désordonné"* alors qu'il pense que tout est bien rangé.

---

## WCAG 2.2 et European Accessibility Act (EAA)

### Les 4 principes POUR

Le WCAG organise ses critères sous 4 principes :

1. **Perceivable** — l'information doit être perceptible (texte alternatif sur images, transcriptions vidéo, contraste suffisant, redimensionnement).
2. **Operable** — l'interface doit être utilisable (navigation clavier, pas de pièges au focus, temps suffisant pour lire).
3. **Understandable** — le contenu et l'interface doivent être compréhensibles (langue déclarée, navigation cohérente, messages d'erreur identifiés et décrits).
4. **Robust** — le code doit être robuste (compatibilité avec les technologies d'assistance, HTML sémantique valide).

### Les 3 niveaux de conformité

- **A** — minimum légal, absence = site inutilisable par certaines personnes.
- **AA** — niveau standard attendu en France et en UE. C'est le niveau imposé par l'EAA.
- **AAA** — niveau exceptionnel, rarement exigé sur tout le site.

### Cadres juridiques d'accessibilité — selon le contexte

Le niveau de rigueur attendu sur l'accessibilité varie selon le contexte juridique de l'organisation auditée. La skill rappelle l'enjeu, l'utilisateur tranche le niveau de rigueur en fonction de ce qu'il sait du client.

**European Accessibility Act (EAA)** — directive européenne (2019/882). Pour les organisations soumises au droit de l'Union européenne, l'EAA impose, depuis le 28 juin 2025, le respect du niveau **WCAG 2.1 AA** (le 2.2 étant en cours d'adoption) pour de nombreux produits et services numériques destinés aux consommateurs particuliers, dont :

- Sites de commerce électronique
- Services bancaires, transport, télécoms
- Livres numériques, billetterie
- Services d'intermédiation (marketplaces, prise de RDV)

**Exceptions importantes** :
- Les TPE (moins de 10 salariés ET moins de 2 M€ CA) sont exemptées sur les services (mais pas sur les produits).
- Les sites destinés exclusivement à un usage professionnel inter-entreprises ne sont pas tous concernés — à vérifier au cas par cas.

**Autres référentiels selon contexte** :
- **ADA (Americans with Disabilities Act)** — États-Unis : interprétée par la jurisprudence comme s'appliquant aux sites web considérés comme "lieu d'accommodation publique". Pas de niveau WCAG explicitement nommé dans la loi mais WCAG 2.1 AA fait référence dans la pratique.
- **AODA (Accessibility for Ontarians with Disabilities Act)** — Ontario : impose WCAG 2.0 AA aux organisations privées de plus de 50 employés.
- **Section 508** — fédéral américain : impose WCAG 2.0 AA aux agences fédérales et à leurs prestataires.
- **RGAA (Référentiel général d'amélioration de l'accessibilité)** — France : impose un niveau équivalent à WCAG 2.1 AA aux services publics et aux entreprises de plus de 250 M€ de CA.

**Ce que ça implique en cadrage** : vérifier le statut juridique du client par rapport au cadre applicable dès la phase 1. Si le client est légalement concerné, l'accessibilité devient un driver de structure, pas un "nice to have" post-production. Si le client n'est pas légalement concerné, l'accessibilité reste recommandée comme bonne pratique mais ne justifie pas les mêmes arbitrages structurels.

### Critères WCAG les plus structurants en cadrage

Ceux qui influencent les décisions dès le cadrage (pas juste la prod) :

- **Contraste** : 4.5:1 pour le texte standard, 3:1 pour le texte large (≥18pt ou ≥14pt bold). Impose des choix de palette.
- **Hiérarchie sémantique** : un seul `<h1>` par page, ordre logique des niveaux. Impose le plan de sections.
- **Navigation clavier** : focus visible, ordre de tabulation logique, pas de pièges. Impose le design des états interactifs.
- **Alternatives textuelles** : `alt` sur images significatives. Impose une discipline éditoriale côté CMS.
- **Cibles de clic** : minimum 24x24px (WCAG 2.2, critère 2.5.8). Impose la taille minimale des CTA mobiles.
- **Identification des entrées de saisie** : labels explicites sur les formulaires. Impose le design des forms.

### Quand mobiliser WCAG/EAA en cadrage

- Phase 1, pour vérifier si le client est assujetti à l'EAA et en tirer les implications structurelles.
- Phase 5, dans la colonne "Contrainte a11y" du template de cadrage, pour chaque section qui a un enjeu d'accessibilité.
- La skill ne produit **pas** un audit WCAG exhaustif — c'est hors scope.

---

## Steve Krug — Don't Make Me Think

Krug a formulé trois principes centraux pour l'ergonomie web, qu'il appelle ses "trois lois" :

### Loi 1 — Ne me fais pas réfléchir
Une page bien conçue doit être **évidente**. Si l'utilisateur doit se demander "qu'est-ce que c'est ?", "est-ce cliquable ?", "où ça me mène ?", c'est un échec de design. *Implications en cadrage : chaque CTA, chaque libellé de menu, chaque section doit être compréhensible sans effort cognitif.*

### Loi 2 — Ça ne fait rien si je clique 3 fois, tant que chaque clic est une décision évidente
Le nombre de clics importe moins que la certitude à chaque clic. Un tunnel en 5 étapes claires bat un tunnel en 2 étapes confuses. *Implications en cadrage : mieux vaut segmenter un formulaire long en 2 étapes lisibles que forcer une saisie unique dense.*

### Loi 3 — Simplifie de moitié le texte, puis encore de moitié
Les utilisateurs **scannent**, ils ne lisent pas. Tout texte doit pouvoir être coupé de 50 % sans perdre l'essentiel. *Implications en cadrage : chaque section de home doit avoir un titre scannable + un sous-texte court. Pas de paragraphes de 200 mots en hero.*

### Quand mobiliser Krug en cadrage

- Phase 2, pour évaluer le ratio texte/visuel et la densité cognitive des pages.
- Phase 5, comme critère de validation du plan de sections (chaque section est-elle scannable en 2 secondes ?).
