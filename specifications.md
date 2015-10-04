# Cahier des charges

## Membres du groupe

* Sacha Bron - *Chef de groupe*
* David Villa - *Chef suppléant*
* Paul Ntawuruhunga
* Yassin Kammoun
* Marc Pellet


## Objectif du projet

L'objectif de ce projet est de concevoir un outil dessin assisté par ordinateur tout en permettant à l'utilisateur de réaliser ses dessins de la manière la plus naturelle possible. En effet, l'utilisateur dessine directement sur sa table ou n'importe quel autre surface plane à l'aide d'un stylet et son dessin est projeté sur son plan de travail. Ce qui donne à l'utilisateur l'impression de dessiner avec un crayon et une feuille.


## Fonctionnalités principales

1. Dessin à l’aide d’un stylet
	
1. Projection de l’image sur le plan de travail
1. Alignement de l’image avec la position du stylet
1. Calibrage du stylet
1. Plan de travail avec barre d'outil

	*Une barre d'outil sera projeté dans une zone du plan travail permettant à l'utilisateur de selectionner un outils.*
	
	* Outils de dessin: crayon, gomme
	* Outils de forme: Ligne droite, carré, cercle
	* Outils de couleur: Palette de couleur
	* Outils de choix d'épaisseur
	
1. Annulation d’une action

	*Une pile d'actions est enregistrée et un bouton dans la barre d'outil permet de remonter cette pile, annulant ainsi les dernières modification apportées au dessin.*
1. Enregistrement et importation du dessin

	*Possibilité d'enregistrer ou importer son dessin au format PNG*
	

## Fonctionnalités supplémentaires

1. Site vitrine
1. Pipette 
1. Remplissage


## Technologies utilisées

* Librarie OpenCV - Pour le suivis du stylet en temps réel.
* Framework Qt - Pour l'interface graphique du plan de travail.

## Plateformes supportées

## Principe de fonctionnement

Ce projet contient trois principales difficultés : la détection de pression sur la table à l'aide du stylet, le suivis de la position du stylet (*tracking*) et la precision.

Pour cela nous avons imaginé un stylet munis d'une mine spéciale. Lors d'une pression sur le plan de travail, cette dernière presse sur un bouton qui enclenche une LED placée proche de la mine. Une caméra placée au-dessus du plan de travail film la scène et envoie l'image au logiciel chargé de suivre la position de la mine du stylet en détectant cette LED.

Le programme de dessin récupère les coordonnées du stylet et les interprètes de manière à pouvoir projeter le dessin sur le plan de travail à l'aide du projecteur vidéo. Un thread de l'application sera consacré au Tracking de la LED, un autre récupérera les coordonnées pour les interpréter sur le plan de travail en fonction de l'outil sélectionné.


## Matériel requis

1.	Stylet *(Prototype conçu par un membre de l'équipe)*

2.	Caméra 

3.	Projecteur vidéo

4. Support *(Pour le placement de la caméra et le projecteur au-dessus du plan de travail)*


## Déploiement

## Planification du projet