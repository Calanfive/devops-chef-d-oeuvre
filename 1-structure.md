# Notes
choix locaux définis en fonction des besoins : s'assurer de la qualité du code et de l'app. (cf C1)
-> config du dépôt, des règles de PR, git flow, convention de nommage (xp groupe pbs fonctionnement, eslint, prettier, etc)
->  s'assurer de la qualité du code et de l'app : tests unitaires, d'intégration, e2e (choix des technos) benchmark comparatif, justif.
BUILD de l'app (sans les dev dep)
Création de l'image : utilité, outils utilisés, choix de l'outil, config (DOCKER)
Image créée : on la dépose dans un repo (DOCKERHUB)
CI : Si faisable en local, à faire dans le GITHUB ACTIONS pour aller vers l'automatisation.	
Du local à l'automatisation : à quoi ça sert, quel outils, choix et config. Schéma + fonctionnement CI / Jenkins
Automatisation de : linter, tests, code coverage, création et dépôt des images (XP PROJET) .yml
Les différents environnements : test, pré-prod, prod
Les mises en prod (manuel sur la base des images docker produites)
Tout ça en une chaîne d'outils automatisé, mais le devops est aussi :
- pratiques entre collabs (XP PROJET : kamban, sprint, PR code review, choix techniques)

# Sommaire
# Contexte

# Introduction au DevOps: 
Pourquoi le devops ? silo, dev, ops, mise en prod, cycle en v.
Avant l'équipe était divisée en silos de compétences, les dev étaient chargé de développer les projets rédigés par les ops...
Ce cycle de mise en prod était un cycle en v...
Aux alentours des années 2000, manifeste agile, 12 principes autour des 4 grandes idées .. nouvelles manières de travailler dans la tech.
Sprint / Itération (schéma cycle itératif et incrémental) ... autre manière de penser son code / Tickets / Kamban / Trello / Github / Git /
Histoire d'internet et des datas (explosion du nb de données) / besoins industriels augmentent = nouveaux standards industriels /  Google 2003 : SRE (cours) / rapprochement DEV/OPS, automatisation, Cloud, IAAS (infrastructure as a service - ex: Neon)
Aujourd'hui, plus une exception mais la règle, d'où l'enjeu pour les devs et le monde de la tech, d'apprendre ces outils et cette culture. (d'où le passage de ma certif).
Dans le cadre de ma formation, j'ai eu l'occasion de travailler sur -PROJET-DESCRIPTION GENERALE- et besoin d'apprendre le DevOps.

Dans le cadre de notre formation CDA, nous développons un projet de groupe appelé GrenoTour. Nous avons souhaité un

Dans le cadre de notre année de formation, nous avons deux examens à présenter : le titre CDA et la certification DevOps. Pour cela, nous avons réalisé un projet fil rouge qui nous a permis de mettre en lumière, les compétences qui ont fait de nous des développeurs et concepteurs d’applications mais également d’utiliser les outils et la méthodologie DevOps sur nos projets.

C’est pour ce dernier point que s’inscrit ce rapport : préciser les logiques DevOps que nous avons mis en œuvre sur le projet chef d’œuvre et en quoi cela nous à aider.

Le projet a débuté tôt dans l’année et nous n’avion pas encore tous les outils pour mener à bien ce projet. Mais à la lecture de ce dossier, mon objectif est de vous démontrer que je possède la connaissance générale et les capacités, de mettre en œuvre une démarche professionnelle et une utilisation judicieuse des outils DevOps.

La problématique choisie est ……
Nous avons utilisé une stack technologique cohérente aux enseignements de cette année et avons spécifiquement choisi d’utiliser ……
Au moment de l’écriture de ce rapport nous avons pu avancé sur … et estimons la réalisation du projet à hauteur de …. %.
Néanmoins, nous avons mis le point sur les outils et méthodes de travail qui nous ont permis de répondre au mieux à vos attentes et à la présentation orale qui se présentera deux semaines plus tard.

Mon projet chef d’œuvre a été réalisé avec …. Il/elle a apporté beaucoup sur la partie ….
De mon côté, j’ai préféré …. Et nous avons fait attention à bien rester synchronisés pour valider ensemble les différents points du référentiel.

Je commencerai par vous présenter 
Puis 
Et enfin, 

Pour chacune de ces étapes, je présenterai :
le contexte et l’objectif principal de ce moment charnière
le cheminent de pensé qui m’a amené à sélectionner une solution
la réalisation de cette solution
le bilan après mise en place

# 1 - Première expérience de groupe
C1 / C2 / C3 / C7
Avant tout, ...

Les outils de versionnement les plus utilisés sont :
- Github
- Gitlab
- Bitbucket
- AWS CodeCommit
- Google Cloud Source Repositories

Le code peut être géré et stocké de façon collaborative. Ces outils permettent également la plannification et une approche orientée "Continuous Intergration" et "Continuous Delivery" (CI/CD) où un gitflow structure l'organisation et les rôles de chacun pour un rendu toujours plus efficace.

Etant donné que nous avons travaillé toute l'année sur Github, nous avons fait le choix de continuer d'expoiter cet outil de versionnement. 
[LOGO GITHUB]

## Fonctionnement du gitflow
Pour notre projet, nous choisissons de créer une branche locale pour chaque nouvelle feature ou correctif à effectuer comme l'indique l'exemple ci-dessous :
[SCREENSHOT MULTIBRANCH GIT]
Définie de façon unanime, cette convention de nommage nous permet de vite nous y retrouver sur le plan organisationnel. 

Une fois travail du développeur accompli et fonctionnel, il ajoute les modifications accomplies à son dépot Git local avec un commit avant des envoyer (push) vers le serveur distant : Github.
La sauvegarde sera envoyer une branche develop. Nous avons préféré créer une branche de travail pour garder la branche principal (ou main) destinée au déploiement final de l'application.
Ci dessous, un exemple de l'architecture de notre travail :
[SCREENSHOT GITFLOW GRAPH]

Notre groupe étant composé de trois développeurs juniors, nous sommes en constants progrès sur le .... entre les différentes tâches à effectuer. 
Gitub nous permet d'utiliser la méthode Kanban. Les tickets y sont déposés par priorité après concertation lors de réunions. Chaque ticket est attribué à une développeur et les statuts sont mis à jour après validation des PR. 
[SCREENSHOT KANBAN GITHUB]
La progression est fluide et la mise en place de sprints courts nous garantit une bonne réactivité face aux difficultés rencontrées.

Cet environnement multi-contributeurs ne pourrait correctement fonctionner sans la mise en place de Pull Request. Ici encore l'outil Github propose un système de validation (ou code review). Lorsqu'elle est maîtrisée, cette fonctionnalité est très efficace et nous fait gagner un temps précieux dans le process d'intégration du code.

Nous évoluons avec la configuration suivante :
[SCEENSHOT CONFIG PR GITHUB)
C'est-à-dire que la sauvegarde ne peut être publiée sur la branche develop uniquement si deux parties ont révisé et validé mon code.
[SCREENSHOT VALIDATION PR)


- Mise en place d'un kanban sur Github et création d'un backlog avec le plus de tâches possibles
définition des règles des sprints (durée, dailies, rétrospectives, etc...)
(Agile, Sprints, retro planning, Kanban, Gantt, les métiers du devops et des entreprises 
digitales (QA, PO, Scrum master, etc...), documentation de lib UI,)

Dans le cadre de l'intégration continue, cette action sera le déclencheur d'une série de tests automatisés : les tests statiques et dynamiques.

Analyse statique
Etape incontournable d'une démarche qualité, l'analyse statique du code passe par l'utilisation d'un Linter. Il s'agit d'un outil d'analyse statique de code source. Il sert à détecter :
- des erreurs (très utile sur des langages interprétés comme JavaScript qui n'ont pas de phase de compilation) ;
- des problèmes de syntaxe et de non-respect de style (tabulation vs espaces, indentation, etc.).

Nous avons choisi l'outil ESLint avec la configuration suivante :
[SCREENSHOT CONFIG ESLINT]
Explications
Une fois de plus, les règles appliqués ont été décidés en groupe afin que chacun puisse évoquer ses préférences.

Nous avons également mis en place un formateur afin d'assurer la cohérence du formatage du code et d'automatiser ce processus. Alors qu'ESLint sera charger de détecter les erreurs, le formateur lui va avoir la capacité de les corriger.

Pour ce faire, il suffit de configurer des règles dans le fichier .prettierrc comme suit : [SCREENSHOT CONFIG PRETTIER] 

Dans le cas de conflits entre ESLint et Prettier, la configuration par ce fichier donnera automatiquement la priorité au Prettier sur le linter.
Ces outils offrent un choix d'utilisation personnalisé grâce à leurs extensions accessibles sur VScode.
L'exemple ci-dessous indique le paramétrage adéquat pour un formatage automatique lors du commit.
[SCREENSHOT CONFIG VSCODE]
Le code ne peut être envoyé sur le repo distant sans avoir été formaté au préalable.

Tests dynamiques 
A ce jour, nous n'avons pas encore mis des tests en place. En revanche, nous projettons d'effectuer en premier lieu des tests unitaires sur la partie Front. L’avantage des tests unitaires est qu’ils sont rapides à écrire et à exécuter. La technologie ReactNative nous impose d'utiliser un outil adapté. Nous avons séléctionné Jest, le framework le plus utilisé en Javascript actuellement. 

Nous restons vigilent sur l'emploi des 'Describe'. Ce qui nous garantit un gain de temps dans la détection et résolution (ou fix) des erreurs. 
Ci-dessous, un exemple de test unitaire effectué lors de notre projet : JEST-EXPO ?
[SCREENSHOT EXEMPLE TEST UNIT] 
Explications

La mise en place de test de bout en bout (ou end to end) va nous permettre de tester chaque fonctionnalité de notre application.
Comparaison de Cypress, Detox, Vitest .. + Choix 
[SCREENSHOT EXEMPLE DE TEST E2E]
Enfin, l'analyse de la code coverage pourrait avoir un rôle important dans le développement de notre application. Or à ce stade, il aurait peu d'intérêt puisque le pourcentage de couverture retournerait un résultat inférieur à 1%.
 
Toutes les étapes vue précédemment vont devenir automatique dans le processus d'intégration (ou CI) grâce à Github Actions. Le choix de cet outil s'est fait naturellement car il nous permet d'utiliser une nouvelle fonctionnalité de Github.

Le configuration du fichier .yml va permettre d'automatiser toutes les étapes de compilation, de vérification de la qualité du code, de test et de packaging. Les étapes (ou jobs) seront lancées successivement lors de chaque nouveau push. Elles définissent un workflow :
[SCREENSHOT .YML]
● Paramétrer les phases d'exécution des tests dans l’environnement de test à chaque push (sur la
branche concernée)

# 2 - MCD et gestion de conflits
C1 / C6 / C7

C1 ++
Nous avons dû effectuer des veilles afin de choisir les technologies adaptées à notre projet. 
Nos connaissances se basaient uniquement sur les cours dispensés cette année. 
Au départ, les recherches étaient fixées par thème sur un ticket: 
[SCREENSHOT] 
Mais du fait d'un temps de traitement anormalement long, nous avons décidé de travailler à plusieurs sur ces themes. 
Nous avons créé un dossier Github (ou repository) dédié à la phase conception du projet et l'apport de nouvelles sources :
[SCREENSHOT]
L'ensemble de la documentation a été rédigé en Markdown (.md).

Après comparaison des différentes technologies, nous avons consulté plusieurs sites et documentations officielles pour nous aider dans la compréhension de nouveaux outils :
- Stack Overflow
- ReactNative (doc)
- Reddit
- YouTube
- Expo (doc)
- Typescript (doc)
- Eslint / Prettier (doc)

Il nous a fallu également faire de la veille sur les outils destinés aux tests. Nous souhaitions utiliser les moyens les plus efficaces et à jour pour éviter les bugs et perte de temps contraignantes. Là encore, les classements d'utilisation des professionnels et la facilité d'utilisation nous a orienté vers les documentations de JEST et ::::::. La mise en place de ces outils m'a permis de mieux comprendre la chronologie et la granularité des tests.

Sur la partie Front, j'ai été en charge :
- de la configuration de l'espace de travail (installation Expo, Typescript, ReactNative)
- du paramétrage des outils d'analyse statiques (ESLint, Prettier)
Afin de garantir une compréhension de mon travail à mes collègues, j'inscrivais les liens des tutos et documentation suivis dans le repo adéquat sur Github.
[SCREENSHOT DEPO]
La configuration des outils statiques nous a permis d'automatiser la qualité du code pendant l'intégration continue. Grâce au paramétrage du fichier .yml, nous n'aurons plus à nous soucis de ces outils.
Une fois les outils sélectionnés, les tickets ont principalement tourné autour du développement de l'application. 

Sur le plan personnel, je m'abonne régulièrement à des comptes LinkedIn. J'en ai ressenti le besoin pour faciliter l'assimilation de nouvelles connaissances durant l'année. 
Ci dessous, un compte que j'affectionne tout particulièrement grâce à des schémas clairs et simples :
[SCREENSHOT LINKEDIN IND]
Il traite de l'ensemble de la chaîne de développement et m'éclaire ainsi sur des points dont je n'avais pas connaissance. Une curiosité en entraîne une autre.

Enfin, en vu de ce rendu, j'ai tenu à jour un journal de bord du projet pour noter: 
- mes travaux : 
- mes ressentis
- les difficultés rencontrés et les solutions mis en place
Au besoin, Github offre la possibilité de revoir le travail accompli via le
[SCREESHOT TICKETS FINIS]
Une fois validés, les tickets sont automatiquement classés dans la colonne correspondante au sein de notre Kanban.


# Documentation et déploiement
C4 / C6 / C7
Storybook = lorsque je push, je mets en ligne ma documentation (comme vercel mais avec React Native)
Je pensais pouvoir utiliser Vercel mais pas compatible. Pour ce faire, j'ai dû effectuer de la veille sur ... 
Cela permet la publication et la mise à disposition de documentations pour les autres particpants du projet.

C4 :
Mise en place et utilisation de Docker localement avec des configurations d'environnement différents -> Docker + matrice/.env+ définition de préprod
● À chaque push (sur la branche concernée) paramétrer les phases de build pour un environnement de
pré-production
● Paramétrer les phases de livraison des builds en environnement de pré-production

# C5 :
Microservice + Duplication des chaînes d'outils CI par services + lib associées
● Décomposer une application monolithique en plusieurs composants et services
● Utiliser un service de conteneurisation pour tous les environnements : dev, test, prod, etc
● Adapter toute la chaîne DevOps à cette nouveauté

# C7
● expliquer et partager la culture DevOps
● expliquer et partager la méthode DevOps : les rôles, les outils, les leviers, etc
● analyser un processus Devops
● préconiser des améliorations à un processus DevOps
Problèmes rencontrés - gestion des conflits (github)
Dev ops comme méthode de travail
- Mise en place d'un kanban sur Github et création d'un backlog avec le plus de tâches possibles
définition des règles des sprints (durée, dailies, rétrospectives, etc...)
(Agile, Sprints, retro planning, Kanban, Gantt, les métiers du devops et des entreprises 
digitales (QA, PO, Scrum master, etc...), documentation de lib UI,)

# Source 
(https://github.com/Calanfive/Documentation/tree/main/DevOps)
(https://betterprogramming.pub/comparing-the-top-three-style-guides-and-setting-them-up-with-eslint-98ea0d2fc5b7)
(https://blog.codacy.com/what-is-a-linter)
(https://www.blogdumoderateur.com/tools/tech/versioning/)
Linter comparaison : (https://www.sitepoint.com/comparison-javascript-linting-tools/)
Documentation JEST EXPO : (https://docs.expo.dev/develop/unit-testing/)

