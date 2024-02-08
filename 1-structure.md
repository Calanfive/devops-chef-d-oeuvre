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

# C1 : 
## Versionnement

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
Cet environnement multi-contributeurs ne pourrait correctement fonctionner sans la mise en place de Pull Request. Ici encore l'outil Github propose un système de validation (ou code review). Lorsqu'elle est maîtrisée, cette fonctionnalité est très efficace et nous fait gagner un temps précieux dans le process d'intégration du code.

Nous évoluons avec la configuration suivante :
[SCEENSHOT CONFIG PR GITHUB)
C'est-à-dire que la sauvegarde ne peut être publiée sur la branche develop uniquement si deux parties ont révisé et validé mon code.
[SCREENSHOT VALIDATION PR)

● Git en ligne de commande
● Respect d’un gitflow
● Utilisation de Github ou Gitlab par exemple

C2 : 
A l'aide de tests : TU + TI, lib de test (x2, e2e)
Outils d'analyse statique : linter
Env de Test : BD de test + .env
● Utilisation d’un linter (natif IDE ou externe)
● Environnement de test (virtuel ou conteneurisé par exemple) Playwright
● Au moins des tests unitaires d’intégrés (pas de minimum de coverage)
● Au moins des tests fonctionnels d’intégrés (pas de minimum de coverage)
● Savoir récupérer la valeur de la couverture du code par les tests
● Exécuter les tests Tests statiques / Tests dynamiques
● Interpréter les résultats et les erreurs
Valeur de couverture : fichier.coverage (JEST ?)

C3 : 
Automatisation de C2 : GHA (yml)
● Configurer l’intégration continue, avec Github Actions ou Gitlab CI/CD
● Paramétrer les phases d'exécution des tests dans l’environnement de test à chaque push (sur la
branche concernée)

C4 :
Mise en place et uttilisation de Docker localement avec des configurations d'environnement différents -> Docker + matrice/.env+ définition de préprod
● À chaque push (sur la branche concernée) paramétrer les phases de build pour un environnement de
pré-production
● Paramétrer les phases de livraison des builds en environnement de pré-production

C5 :
Microservice + Duplication des chaînes d'outils CI par services + lib associées
● Décomposer une application monolithique en plusieurs composants et services
● Utiliser un service de conteneurisation pour tous les environnements : dev, test, prod, etc
● Adapter toute la chaîne DevOps à cette nouveauté

C6 : Veille techno + monitoring (métier SRE?) 	
Benchmark
● définir des objectifs à sa veille ou encore des thématiques de veille
● planifier les temps de veille : durée, fréquence
● organiser sa collecte d’information : outils de curation, outils de sauvegarde, etc
● organiser le partage voir la diffusion des informations pertinantes

C7 : Accompagner les collaborateurs au sein de l’équipe projet dans la sensibilisation et l’acculturation des méthodes d’organisation et de production DevOps de manière à optimiser le cycle de livraison d’un projet
● expliquer et partager la culture DevOps
● expliquer et partager la méthode DevOps : les rôles, les outils, les leviers, etc
● analyser un processus Devops
● préconiser des améliorations à un processus DevOps
Problèmes rencontrés - gestion des conflits (github)
  

# Source 
(https://github.com/Calanfive/Documentation/tree/main/DevOps)
(https://betterprogramming.pub/comparing-the-top-three-style-guides-and-setting-them-up-with-eslint-98ea0d2fc5b7)
(https://blog.codacy.com/what-is-a-linter)
(https://www.blogdumoderateur.com/tools/tech/versioning/)
