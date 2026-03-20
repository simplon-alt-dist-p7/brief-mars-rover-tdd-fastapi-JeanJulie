---
date: 2026-03-20
tags:
  - simplon
  - brief
  - tdd
  - python
  - fastapi
  - api
status: draft
note_type: brief
---

# Brief - API Mars Rover en TDD avec Python et FastAPI

## Métadonnées

- Statut : Assigné
- Langue : FR
- Auteur : Jean-Baptiste Lavisse
- Date de création : 2026-03-20

## Objectif

Développer une petite API REST en Python avec FastAPI en appliquant une démarche TDD de bout en bout.

L'objectif n'est pas de produire une API énorme. L'objectif est de travailler en binôme, d'avancer par petits cycles de tests, puis de faire émerger une logique métier propre autour d'un rover qui se déplace sur une grille.

## Technologies et notions

- Python 3
- FastAPI
- Pytest
- Tests unitaires
- Tests d'API
- Pair programming
- Red, green, refactor

## Référentiels et ressources

- Référentiel : [2023] Concepteur⋅rice développeur⋅se d'applications
- Ressource :
  - documentation FastAPI
  - documentation Pytest

## Contexte du projet

Une équipe doit prototyper l'API de pilotage d'un rover d'exploration.

Le rover évolue sur une grille rectangulaire. Il possède une position, une orientation et reçoit une suite de commandes.

L'API doit permettre :

- de créer un rover avec un état initial
- d'envoyer une suite de commandes
- de récupérer l'état courant du rover

Le rover doit pouvoir :

- avancer
- reculer
- tourner à gauche
- tourner à droite
- rester dans les limites de la grille
- détecter les obstacles fournis dans la configuration

## Règles fonctionnelles

### Grille

- la grille possède une largeur et une hauteur
- les coordonnées minimales sont `0,0`
- un rover ne peut pas sortir des limites de la grille

### Rover

- un rover possède un identifiant
- un rover possède une position `x, y`
- un rover possède une direction parmi `N`, `E`, `S`, `W`

### Commandes

- `F` : avancer d'une case
- `B` : reculer d'une case
- `L` : pivoter à gauche
- `R` : pivoter à droite

### Obstacles

- des obstacles peuvent être placés sur la grille
- si un obstacle bloque le prochain déplacement, le rover s'arrête
- l'API doit retourner l'état final atteint et indiquer qu'un obstacle a été rencontré

### Validation

- une direction inconnue doit être rejetée
- une commande inconnue doit être rejetée
- une position initiale hors grille doit être rejetée

## Périmètre attendu

Le périmètre minimum attendu pour cette séance :

- un point d'entrée pour créer un rover
- un point d'entrée pour envoyer une suite de commandes à un rover existant
- un point d'entrée pour consulter l'état courant d'un rover

Le nom précis des routes, la structure exacte des payloads et l'organisation interne du code font partie de vos choix de conception.

En revanche, la logique métier ne doit pas être noyée dans les routes HTTP.

## Modalités pédagogiques

- Travail en binôme
- Durée : une petite après-midi
- Pair programming conseillé :
  - un driver écrit
  - un navigator relit, questionne et garde le cap TDD
  - inversion régulière des rôles

## Modalités d'évaluation

- Démonstration de l'API
- Vérification des tests
- Lecture rapide du code en binôme
- Vérification du respect d'une démarche incrémentale

## Livrables

- Un dépôt Git contenant le code
- Une API exécutable localement
- Une suite de tests automatisés
- Un `README.md` avec les étapes de lancement

## Critères de performance

- Les tests passent
- Les règles métier principales sont couvertes
- Le code montre une séparation claire entre domaine et API
- La validation des entrées est correcte
- Les commits sont cohérents
- La démonstration est fluide

## Contraintes de travail

- Commencer par les tests
- Avancer par petites étapes
- Ne pas coder plusieurs règles d'un coup
- Refactorer seulement quand les tests sont au vert
- Ne pas partir sur une base de données
- Ne pas ajouter d'authentification
- Ne pas ajouter d'interface front

## Aide au démarrage

Vous pouvez démarrer par une simple logique métier locale avant de l'exposer en HTTP.

Questions utiles :

- comment représenter l'orientation du rover ?
- comment faire évoluer la position sans casser les règles de la grille ?
- à quel moment une règle relève du domaine et non de FastAPI ?
- quel est le prochain plus petit test utile ?

## Situation professionnelle liée

[[2026-03-20-situation-pro-concevoir-une-api-metier-en-tdd]]

## Besoin visé ou problème rencontré

Une équipe de développement doit concevoir rapidement un service fiable, testable et maintenable autour d'une logique métier simple mais non triviale.

## Compétences visées

- C1. Installer et configurer son environnement de travail en fonction du projet
- C3. Développer des composants métier
- C4. Rechercher de façon méthodique une ou des solutions au problème rencontré
- C6. Définir l'architecture logicielle d'une application
- C9. Préparer et exécuter les plans de tests
