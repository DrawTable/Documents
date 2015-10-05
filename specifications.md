# Cahier des charges

Ce document constitue le cahier des charges du projet de groupe.

## Membres du groupe

- Sacha Bron - *Chef de groupe*
- David Villa - *Chef suppléant*
- Paul Ntawuruhunga
- Yassin Kammoun
- Marc Pellet


## Objectif du projet

L'objectif de ce projet est de concevoir un outil dessin assisté par ordinateur permettant à l'utilisateur de réaliser ses dessins de la manière la plus naturelle possible. À terme, l'utilisateur dessinera directement sur sa table ou n'importe quelle autre surface plane à l'aide d'un stylet et son dessin sera projeté sur son plan de travail, donnant à l'utilisateur l'impression de dessiner avec un crayon et une feuille.


## Fonctionnalités principales

- Dessin à l’aide d’un stylet
- Projection de l’image sur le plan de travail
- Alignement de l’image avec la position du stylet
- Calibrage du stylet
- Plan de travail avec barre d'outil

	*Une barre d'outil sera projeté dans une zone du plan travail permettant à l'utilisateur de selectionner un outil.*
	
	- Outils de dessin: crayon, gomme
	- Outils de forme: Ligne droite, carré, cercle
	- Outils de couleur: Palette de couleurs
	- Outils de choix d'épaisseur
	
- Annulation d’une action

	*Une pile d'actions est enregistrée et un bouton dans la barre d'outil permet de remonter cette pile, annulant ainsi les dernières modifications apportées au dessin.*
- Enregistrement et importation du dessin

	*Possibilité d'enregistrer ou importer son dessin au format PNG*
	

## Fonctionnalités supplémentaires

- Site vitrine
- Pipette 
- Remplissage

## Technologies utilisées

- Librarie OpenCV - Pour le suivis du stylet en temps réel.
- Framework Qt - Pour l'interface graphique du plan de travail.

## Plateformes supportées

De par la nature du framework Qt, l'application est automatiquement multiplateforme; elle est donc supportée par les environnements usuels. Il s'agit entre autres des éditions Windows, des systèmes Mac OS X et des différentes distributions Linux. Un simple travail de recompilation du code source sur l'environnement désiré permet de disposer d'une version compatible de l'application.

## Principe de fonctionnement

Ce projet contient trois principales difficultés: la détection de contact du stylet sur la table, le suivis de la position du stylet (*tracking*) et la précision de l'entier du système.

Pour cela nous avons imaginé un stylet munis d'une mine spéciale. Lors d'une pression sur le plan de travail, cette dernière presse sur un bouton qui enclenche une diode électroluminescente placée proche de la mine. Une caméra placée au-dessus du plan de travail film la scène et envoie l'image au logiciel chargé de suivre la position de la mine du stylet en détectant cette LED.

Le programme de dessin récupère les coordonnées du stylet et les interprètes de manière à pouvoir projeter le dessin sur le plan de travail à l'aide du projecteur vidéo.

L'application comportera différents threads: un thread de l'application sera consacré au tracking de la LED, un autre récupérera les coordonnées pour les interpréter sur le plan de travail en fonction de l'outil sélectionné.


## Matériel requis

- Stylet *(Prototype conçu par un membre de l'équipe)*

- Caméra 

- Projecteur vidéo

- Support *(Pour le placement de la caméra et le projecteur au-dessus du plan de travail)*


## Déploiement

Le déploiement de l'application suit la procédure standard des environnements supportés:

- Pour un environnement Windows, le déploiement se réalise par le biais d'un programme d'installation. 
- Pour un environnement Mac OS X, le déploiement se réalise par le biais d'un fichier DMG.
- Pour une distribution Linux donnée, le déploiement se réalise par le biais d'un paquetage.

La mise en place du matériel requis est décrite par la procédure suivante:

1. Disposer le support de travail.
2. Poser le stylet sur le support de travail.
3. Placer la caméra au-dessus du support de travail.
4. Placer le projecteur vidéo au-dessus du support de travail.

Le schéma suivant illustre un environnement de travail idéal:

*à compléter... dessiner l'ébauche d'une pièce avec un mannequin, un stylet, une table, une chaise, une caméra, un beamer et un pc.*
