# OSIRIS-RWD

OSIRIS est un projet qui a pour but de favoriser le partage des données et poser des bases communes pour permettre l’interopérabilité en oncologie. OSIRIS RWD (pour Real World Data) est une adaptation aux données « en vie réelle » du modèle OSIRIS publié en 2021 ( ). 

Le modèle OSIRIS RWD inclut un Minimum Data Set (MDS) de données cliniques, complété par un module génomique et un MDS de données concernant l’imagerie (OSIRIS – imagerie) et la radiothérapie (OSIRIS – RT). 

Le MDS clinique a été défini sur la base d’un consensus d’experts. Il est complété du guide d’implémentation qui a été élaboré en parallèle à la liste des items.

Les MDS Imagerie et radiothérapie ont été définis sur la base d’un consensus d’experts (ingénieurs en imagerie médicale, physiciens médicaux, radiothérapeutes). Ils sont complétés d’un modèle de donnée conceptuel et logique dérivé du projet CodeX d’HL7 : https://hl7.org/fhir/us/codex-radiation-therapy/. L’ensemble de la documentation est disponible sur le lien suivant : https://github.com/InstitutNationalduCancer

Avec la mise en place d’un modèle de données clinique (modèle conceptuel, modèle logique et modèle physique), l’objectif est une mise en œuvre opérationnelle dans une base de données « open source ». Le choix s’est porté sur PostgreSQL, système de gestion de base de données relationnelle (SGBDR). 

En aval de la base de données OSIRIS RWD, il est prévu d’extraire et transformer ces données vers d’autres formats : OMOP (pour le partage) et FHIR (pour la communication et le retour au dossier médical). 

A terme, un des objectifs du projet OSIRIS RWD est de permettre l’interopérabilité entre les systèmes d’information hospitaliers (SIH) et les entrepôts de données de santé (EDS) hospitaliers. L’interopérabilité s’entend sous tous ses aspects : technique, syntaxique, sémantique et juridique.

- Technique : les données sont indépendantes de l’infrastructure des systèmes et des protocoles de communication
- Syntaxique : le modèle de données, le format des tables et le nom de la variable sont documentés
- Sémantique : les données sont codées de manière standardisée et normalisée avec un même sens donné aux codes et à la description de la variable
- Juridique avec un même respect des règles et des politiques de confidentialité pour être conforme au RGPD.

Dans ce document sont définies les règles d’alimentation de la base de données qui constituent le guide d’implémentation. L’alimentation de la base de données est sous la responsabilité des établissements de santé et des gestionnaires des EDS hospitaliers.

Ce document a pour objet de détailler les items du MDS et de proposer les modalités d’alimentation qui vont de la source (le SIH) vers la base de données pour une alimentation automatique. Différents points sont abordés en fonction de la complexité des items :

- Définition de la variable : à quelle entité elle appartient (patient, tumeur, traitement),
- Choix des terminologies (Ex : CIMO-3, LOINC, SNOMED CT).
- Définir la source : dossier médical textuel ou donnée structurée, issu de quel type de compte-rendu du dossier médical en tenant compte des possibilités de structuration par des techniques de traitement automatique du langage naturel (TALN).

Le guide sera complété de règles pour une alimentation « manuelle » pour permettre une mesure de la qualité des données alimentées automatiquement.
