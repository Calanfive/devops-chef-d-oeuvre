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



Dans le cadre de notre année de formation, nous avons deux examens à présenter : le titre CDA et la certification DevOps. Pour cela, nous avons réalisé un projet fil rouge qui nous a permis de mettre en lumière, les compétences qui ont fait de nous des développeurs et concepteurs d’applications mais également d’utiliser les outils et la méthodologie DevOps sur nos projets.

C’est pour ce dernier point que s’inscrit ce rapport : préciser les logiques DevOps que nous avons mis en œuvre sur le projet chef d’œuvre et en quoi cela nous à aider.

Le projet a débuté tôt dans l’année et nous n’avion pas encore tous les outils pour mener à bien ce projet. Mais à la lecture de ce dossier, mon objectif est de vous démontrer que je possède la connaissance générale et les capacités, de mettre en œuvre une démarche professionnelle et une utilisation judicieuse des outils DevOps.

La problématique choisie est ……
Nous avons utilisé une stack technologique cohérente aux enseignements de cette année et avons spécifiquement choisi d’utiliser ReactNative.
Au moment de l’écriture de ce rapport, nous estimons la réalisation du projet à hauteur de 90. %.
Néanmoins, nous avons mis le point sur les outils et méthodes de travail qui nous ont permis de répondre au mieux à vos attentes et à la présentation orale qui se présentera deux semaines plus tard.

Dans le cadre de notre projet de fin d'étude du titre Concepteur Developpeur d'Application, nous avons formé un groupe de travail composé de Karim Sekri, Aymeric Rambaud et Camille Le Lan, où chacun a réussi à trouver sa place. Nous avons fait attention à bien rester synchronisés pour valider ensemble les différents points du référentiel.

Dans un monde ultraconnectée, où gagner du temps est la priorité de tous, il nous a paru intéressant de travailler sur un projet d'application de tourisme 100% mobile.
Cet outil s'adresse aux visiteurs de la ville de Grenoble et permet la génération d'itinéraires personnalisables en fonction des centres d'intérêt de chacun. Le gain de temps est certain. Après quelques clics, vous n'aurez plus qu'à suivre l'itinéraire choisie pendant une durée voulue.

Ce dossier comprendra trois points : 
- notre premier projet en groupe
- qualité, tests et intégration continue
- documentation et mise en place de veille 

Pour chacune de ces étapes, je présenterai :
- le contexte et l’objectif principal de ce moment charnière
- le cheminent de pensé qui m’a amené à sélectionner une solution
- la réalisation de cette solution
- le bilan après mise en place

# 1 - Première expérience de groupe
C1 / C2 / C3 / C7

Analyse statique
C2 / C3 / C7

Tests dynamiques 
C4 / C6 / C7


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

# Source 
(https://github.com/Calanfive/Documentation/tree/main/DevOps)
(https://betterprogramming.pub/comparing-the-top-three-style-guides-and-setting-them-up-with-eslint-98ea0d2fc5b7)
(https://blog.codacy.com/what-is-a-linter)
(https://www.blogdumoderateur.com/tools/tech/versioning/)
Linter comparaison : (https://www.sitepoint.com/comparison-javascript-linting-tools/)
Documentation JEST EXPO : (https://docs.expo.dev/develop/unit-testing/)

