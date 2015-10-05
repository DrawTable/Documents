# Cahier des charges

Ce document constitue le cahier des charges du projet de groupe.

## Contexte

Ce projet de groupe se déroule dans le cadre de la formation Bachelor HES de la Haute-Ecole d'Ingénierie et de Gestion du canton de Vaud. Il compte pour une unité d'enseignement du plan d'étude de l'orientation Informatique logiciel (IL) du département des Technologies de l'Information et de la Communication (TIC) de l'école. Il se réalise durant le cinquième semestre de l'année de formation 2015/16.

## Membres du groupe

Les personnes suivantes constituent les membres du groupe de l'équipe de projet:

- Sacha Bron - *Chef de groupe*
- David Villa - *Chef suppléant*
- Paul Ntawuruhunga
- Yassin Kammoun
- Marc Pellet

## Objectif du projet

L'objectif de ce projet est de concevoir un outil de dessin assisté par ordinateur permettant à l'utilisateur de réaliser ses dessins de la manière la plus naturelle possible. À terme, l'utilisateur dessinera directement sur sa table ou n'importe quelle autre surface plane à l'aide d'un stylet et son dessin sera projeté sur son plan de travail, donnant à l'utilisateur l'impression de dessiner avec un crayon et une feuille.

## Fonctionnalités principales

Les fonctionnalités principales du projet sont les suivantes:

- Dessin à l’aide d’un stylet.
- Projection de l’image sur le plan de travail.
- Alignement de l’image avec la position du stylet.
- Calibrage du stylet.
- Plan de travail avec barre d'outils.
	+ Une barre d'outils sera projetée dans une zone du plan travail permettant à l'utilisateur de sélectionner un outil.
		* Outils de dessin: crayon, gomme.
		* Outils de forme: ligne droite, carré, cercle.
		* Outils de couleur: palette de couleurs.
		* Outils de choix d'épaisseur.
- Annulation d’une action
	+ Une pile d'actions est enregistrée et un bouton dans la barre d'outils permet de remonter cette pile, annulant ainsi les dernières modifications apportées au dessin.
- Enregistrement et importation du dessin
	+ Possibilité d'enregistrer ou importer son dessin au format PNG.

## Fonctionnalités supplémentaires

Les fonctionnalités supplémentaires du projet sont les suivantes:

- Site vitrine.
- Pipette.
- Remplissage.
- Rétablissement d'une action.

## Mockup

La figure suivante illustre une ébauche de l'interface graphique utilisateur devant correspondre au plan de travail:

![Interface graphique utilisateur](ui.png)

L'interface graphique utilisateur est divisée en trois parties à savoir la barre des menus, la barre d'outils et la zone de dessin.

## Prototype du stylet

Le prototype de stylet est conçu par le chef de projet. Sa conception nécessite les composants suivants:

- LED.
- Un interrupteur.
- Une résistance.
- Une batterie.
- Un boîtier.

La figure suivante propose une ébauche de prototype du stylet:

![Prototype du stylet](schama-stylus.png)

## Principe de fonctionnement

Ce projet contient trois principales difficultés: la détection de contact du stylet sur la table, le suivi de la position du stylet (*tracking*) et la précision de l'entier du système.

Pour cela nous avons imaginé un stylet muni d'une mine spéciale. Lors d'une pression sur le plan de travail, cette dernière presse sur un bouton qui enclenche une diode électroluminescente placée proche de la mine. Une caméra placée au-dessus du plan de travail filme la scène et envoie l'image au logiciel chargé de suivre la position de la mine du stylet en détectant cette LED.

Le programme de dessin récupère les coordonnées du stylet et les interprète de manière à pouvoir projeter le dessin sur le plan de travail à l'aide du projecteur vidéo.

L'application comportera différents threads: un thread de l'application sera consacré au tracking de la LED, un autre récupérera les coordonnées pour les interpréter sur le plan de travail en fonction de l'outil sélectionné.

## Public-cible

L'application vise avant toute chose tout amateur de dessin souhaitant se passer d'une feuille. 

## Technologies utilisées

Les technologies utilisées pour le développement de l'application et le suivi du stylet sont les suivantes:

- Librairie OpenCV - Pour le suivi du stylet en temps réel.
- Framework Qt - Pour l'interface graphique du plan de travail.

## Matériel requis

Les points suivants constituent le matériel requis pour l'utilisation de l'application.

- Un prototype de stylet faisant office d'outil de dessin.
- Une caméra permettant de traquer les mouvements du stylet. 
- Un projecteur vidéo permettant de retranscrire le dessin de l'utilisateur.
- Un plan de travail permettant de dessiner.
- Un support prévu pour la disposition de la caméra et du projecteur au-dessus du plan de travail.

## Plateformes supportées

De par la nature du framework Qt, l'application est automatiquement multiplateforme; elle est donc supportée par les environnements usuels. Il s'agit entre autres des éditions Windows, des systèmes Mac OS X et des différentes distributions Linux. Un simple travail de recompilation du code source sur l'environnement désiré permet de disposer d'une version compatible de l'application.

## Déploiement

### Installation de l'application

Le déploiement de l'application suit la procédure standard des environnements supportés:

- Pour un environnement Windows, le déploiement se réalise par le biais d'un programme d'installation. 
- Pour un environnement Mac OS X, le déploiement se réalise par le biais d'un fichier DMG.
- Pour une distribution Linux (Arch), le déploiement se réalise par le biais d'un paquetage.

### Mise en place du matériel

La mise en place du matériel requis est décrite par la procédure suivante:

1. Disposez le support de travail.
2. Posez le stylet sur le support de travail.
3. Placez la caméra au-dessus du support de travail.
4. Placez le projecteur vidéo au-dessus du support de travail.

Les schémas suivants illustrent un environnement de travail idéal:

![Vue de côté d'un environnement idéal](side.png)

![Vue en perspective d'un environnement idéal](sideview.png)

## Déroulement du projet

### Planification des tâches

Le diagramme de Gantt qui suit présente la planification des tâches du projet:

![Planification des tâches](planification.png)

### Description des tâches

Les points suivants constituent un bref descriptif des tâches du projet:

- Enregistrement d'une vidéo de test
	+ Afin de pouvoir tester les différents outils du logiciel de dessin avant que l'outil de tracking ne soit terminé, une vidéo contenant différents mouvements sera enregistrée.
- Apprentissage d'OpenCV
	+ Pour toutes les opérations de tracking du stylet, nous allons utiliser la librairie OpenCV. Il sera donc nécessaire de prendre le temps d’en apprendre les bases avant de se lancer à corps perdu dans l’implémentation.
- Construction d'un stylet
	+ Un stylet de notre propre création sera utilisé pour cette application, le matériel nécessaire à la fabrication de ce dernier est détaillé dans la description du prototype du stylet.
- Tracking du stylet
	+ A l’aide d’une caméra, nous détecterons les mouvements du stylet, il faudra donc récupérer ces informations et les transmettre au logiciel de dessin.
- Apprentissage de Qt
	+ Apprentissage des librairies Qt pour ce qui concerne principalement les interfaces graphiques et les librairies de dessin.
- Création de l’interface graphique
	+ Conception de l’interface graphique du logiciel. Celle-ci contiendra un menu permettant d’importer/exporter des images, d’un plan de travail sur lequel travailler ainsi qu’une boîte à outils contenant différentes fonctionnalités telles que le crayon, la gomme, une palette de couleurs, le choix de l’épaisseur du trait.
- Tracking intermédiaire de la souris
	+ Afin de permettre de tester le bon fonctionnement de l’implémentation des différents outils, ceci d’une manière accessible à tous les développeurs, il faut implémenter une fonctionnalité permettant de dessiner à l’aide de la souris.
- Création du modèle de l’image
	+ Conception et création du modèle qui sera utilisé par le logiciel pour représenter notre image.
- Implémentation des outils
	+ Implémentation des fonctionnalités obligatoires disponibles dans notre boîte à outils. Se référer à la description des fonctionnalités pour en connaître l'inventaire.
- Enregistrement des dessins
	+  Exportation de notre représentation de l’image en une image au format .PNG.
- Modélisation et affichage du dessin
	+  Implémentation des méthodes gérant l’affichage et la modélisation de notre image.
- Calibrage du projecteur avec les données du stylet
	+ Calibrage permettant de faire concorder la position de l’image projetée avec la position effective du stylet.
- Dessin selon la vidéo de test
	+ Utilisation d’une vidéo de test pré-enregistrée utilisant les méthodes de tracking implémentées permettant de tester les différents outils sans pour autant avoir le matériel à disposition.
- Liaison entre le stylet et le logiciel
	+ Liaison entre les données collectées par le système de tracking avec les méthodes d’affichage du logiciel.