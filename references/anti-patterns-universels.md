# Anti-patterns universels du web

Ce fichier liste les anti-patterns **objectifs** qu'un cadrage UX sérieux doit éviter, indépendamment du goût ou de l'identité du professionnel qui utilise la skill. Il ne traite pas des partis-pris esthétiques (dreamcore SaaS, skeuomorphisme, material design, brutalism, etc.) qui relèvent de la sensibilité de chacun — ces questions sont à traiter dans une skill d'identité professionnelle utilisée en parallèle, ou via le calibrage initial proposé à la première invocation.

Les anti-patterns listés ici sont ceux pour lesquels **aucun bon argument ne tient** : ils nuisent à la compréhension, à la conversion, à l'accessibilité, ou à la confiance du visiteur, quel que soit le secteur.

---

## 1. Copy et messages

### "Passionnés / À l'écoute / Sur-mesure / Votre partenaire de confiance"
Formulations vides, utilisées par 80 % des concurrents du client. Aucun pouvoir de différenciation. À remplacer systématiquement par une promesse spécifique appuyée par une preuve.

### Lorem Ipsum visible en production
Signal d'amateurisme brutal. S'il reste une section non rédigée, la cacher ou la remplir, jamais la laisser en Lorem.

### Jargon métier non traduit
Parler la langue du client final, pas celle du métier. *"Prestation d'accompagnement global multi-disciplinaire"* dit à quelqu'un qui cherche un coach = friction cognitive immédiate.

### Texte marketing en gras partout
Si tout est mis en emphase, rien ne l'est. L'emphase (gras, italique, couleur) perd sa fonction quand elle couvre plus de 15-20 % du texte.

### Slogan creux en hero
*"Bienvenue sur notre site !"*, *"Votre satisfaction, notre priorité"*. Un hero qui n'annonce pas ce que fait l'entreprise fait perdre des secondes de qualification — et souvent le visiteur.

### Verbes à l'infinitif dans les CTA
*"En savoir plus"*, *"Découvrir"*, *"Consulter"*. CTA faibles qui ne disent pas ce qui se passe après le clic. Préférer la première personne (*"Je veux mon devis"*, *"Obtenir ma démo"*) ou l'impératif contextuel (*"Demander un devis"*).

---

## 2. Navigation et architecture

### Plus de 7 items dans le menu principal
Loi de Hick : au-delà de 7 items, le temps de décision explose. Si le client a vraiment 15 pages importantes, les grouper en catégories avec menus déroulants — mais idéalement repenser la hiérarchie.

### Burger menu en desktop sans raison
Le burger est une convention mobile. L'utiliser en desktop cache la navigation pour économiser de la place visuelle — mauvais compromis, sauf contexte très spécifique (éditorial immersif).

### Absence de lien vers l'accueil via le logo
Convention de web forte depuis 20 ans (loi de Jakob). Un logo non cliquable ou qui ne ramène pas à la home crée un pont cognitif inutile.

### "Page contact" introuvable depuis la home
Friction d'acquisition directe. Le visiteur qui veut contacter ne doit pas scroller longtemps pour trouver le moyen de le faire. Un lien contact doit être visible dans le header ou le footer, toujours.

### Sitemap dont la structure ne correspond à aucun parcours utilisateur
Pages créées "parce qu'il en fallait une" (ex : page "Nos valeurs" isolée) sans rôle dans un parcours identifié. Un sitemap bien pensé = chaque page a une raison d'être visitée.

---

## 3. Hero / above the fold

### Carrousel automatique en hero
Réduit fortement le taux d'interaction avec le contenu du hero (études Nielsen Norman Group depuis 10 ans). Les visiteurs ne voient souvent que le premier slide, et la rotation automatique crée de la frustration. Si plusieurs messages cohabitent, préférer un message unique ou un choix explicite par onglets.

### Hero sans proposition de valeur claire en moins de 5 secondes
Le visiteur doit comprendre **quoi** (quelle activité), **pour qui** (quelle cible), **pourquoi nous** (pourquoi ici et pas ailleurs) en moins de 5 secondes. Un hero qui ne répond pas aux trois questions est un hero qui perd du trafic.

### Vidéo en hero sans bouton pause / mute par défaut
Violation d'accessibilité (WCAG 1.4.2, 2.2.2) et de confort utilisateur. Si vidéo il y a, elle doit être muette par défaut, avec contrôles accessibles.

### Pop-up agressive à l'arrivée sur la page
Cookie banner qui couvre tout le hero, modal "abonne-toi à la newsletter" dans les 2 secondes, chatbot qui ouvre un message automatique avant que le visiteur n'ait lu un mot. Friction d'entrée qui fait grimper le rebond.

---

## 4. Tunnel et conversion

### Formulaire de contact de plus de 5 champs en premier contact
Chaque champ supplémentaire réduit le taux de complétion (principe établi par de nombreux A/B tests publics). Pour un premier contact, se limiter à nom, email/téléphone, projet. Le reste (budget, délais, détails) peut venir en étape 2.

### Champs obligatoires non signalés
Ou inversement, trop de champs obligatoires. Les astérisques doivent être visibles et expliqués. Idéalement, limiter les champs obligatoires au minimum absolu.

### CTA contradictoires dans la même vue
Un bouton *"Demander un devis"* + un bouton *"Télécharger le catalogue"* + un bouton *"Prendre RDV"* au même niveau visuel = personne ne sait lequel est l'action principale. Un CTA primaire, un secondaire maximum par vue.

### Absence de feedback après soumission de formulaire
Soit l'utilisateur n'est pas sûr que ça a marché (page qui se recharge sans message), soit il doute (message trop discret). Un message de confirmation explicite + email de suivi est le minimum.

### Page "merci" qui ne relance pas l'utilisateur
Opportunité gâchée. La page merci est une des plus lues du site (le visiteur y arrive motivé). Elle doit contenir au minimum : confirmation claire, prochaine étape attendue, un contenu utile (témoignage, case study, contenu de valeur).

---

## 5. Performance et technique

### Temps de chargement mobile > 3 secondes sur 4G
Bug critique en 2025. Au-delà de 3 secondes, le taux de rebond double. À tester systématiquement via PageSpeed Insights ou WebPageTest.

### Images non optimisées
JPEG 3 Mo pour un visuel en hero, PNG 5 Mo sur une page produit. Formats modernes (WebP, AVIF) attendus en 2025. Les images doivent être servies en résolution adaptée au device (srcset).

### Scripts tiers bloquants
Trackers, chatbots, A/B testing tools qui chargent en synchrone et bloquent le rendu. Chaque script tiers doit être audité pour son impact performance.

### Absence de HTTPS
Inacceptable en 2025. Même un site vitrine sans formulaire doit être en HTTPS (Chrome marque les sites HTTP comme "non sécurisés").

### Erreurs console visibles en navigation normale
Signal d'hygiène tech faible. À défaut d'être visible par le visiteur, c'est un indicateur que la maintenance sera difficile.

---

## 6. Accessibilité (rappels critiques)

### Contraste texte insuffisant
En dessous de 4.5:1 sur texte standard, le texte devient illisible pour une partie significative des visiteurs (notamment seniors et malvoyants). Violation WCAG AA.

### Absence de `alt` sur les images significatives
Les lecteurs d'écran ne peuvent pas décrire ces images. Violation WCAG 1.1.1. Pour les images purement décoratives, `alt=""` explicite.

### Navigation clavier cassée (pièges au focus, ordre illogique)
Impossible de naviguer le site sans souris. Violation WCAG 2.1. Test rapide : naviguer la home uniquement avec Tab.

### Placeholders utilisés comme labels de formulaire
Le placeholder disparaît quand l'utilisateur commence à taper. Les champs de formulaire doivent avoir un label visible et persistant.

### Textes en image (sans alternative HTML)
Le texte contenu dans une image n'est ni indexable ni lisible par les lecteurs d'écran. Remplacer par du vrai texte HTML stylé en CSS.

---

## 7. Confiance et réassurance

### Absence totale de preuves sociales
Pas de témoignages, pas de logos clients, pas de case studies, pas de chiffres de réalisations. Un visiteur sans repères de confiance rebondit.

### Témoignages anonymes ou génériques
*"Super entreprise, je recommande ! — Marie, cliente satisfaite"*. Zéro valeur de réassurance. Un bon témoignage a un nom, un prénom, une fonction, idéalement une photo, et un contenu spécifique.

### Mentions légales introuvables ou incomplètes
Obligation légale en France. Absence ou incomplétude = risque juridique + signal d'amateurisme. Lien vers mentions légales toujours visible en footer.

### Politique de cookies absente ou non conforme RGPD
Non seulement une obligation légale, mais aussi un signal de professionnalisme. Un bandeau cookies mal implémenté (consentement forcé, pas de refus possible, cookies avant consentement) est doublement pénalisant.

### Faux avis / faux témoignages
Repérables à l'oeil exercé (toujours 5 étoiles, style d'écriture identique, personnages stéréotypés). Destructeurs de confiance quand ils sont repérés — et ils le sont souvent.

---

## Comment la skill utilise ce fichier

Charger `anti-patterns-universels.md` en phase 5, au moment de finaliser le livrable. Parcourir les 7 sections et vérifier :

1. **Dans le diagnostic de l'existant** : quels anti-patterns sont présents sur le site actuel ? Ceux-là doivent être dans la liste des "bugs critiques à corriger avant redesign" ou dans les "décisions structurelles à tenir".

2. **Dans les recommandations du redesign** : est-ce qu'une de mes recommandations tombe dans un anti-pattern ? Si oui, la réviser.

Si la skill détecte qu'elle a elle-même proposé un anti-pattern dans le livrable, le signaler à l'utilisateur avec une mention explicite *"Signalement : cette recommandation tombe dans l'anti-pattern [X]. Alternative proposée : [Y]."*
