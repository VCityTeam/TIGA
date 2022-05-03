# TIGA

**THINK & DO TANK Sciences, Sociétés et Industrie**

**Fiche-action RECHERCHE du projet TIGA de la Métropole de Lyon Saint-Etienne.**

Cette action a pour objectif de déceler, prototyper, expérimenter et valoriser sous un horizon de 3 ans des méthodes et des outils innovants pour la médiation industrielle. Elle vise à identifier des verrous scientifiques et proposer des solutions innovantes (supports matériels, numériques et méthodologiques) pour une interaction fluide et continue entre les acteurs du territoire.
L’action 14 engage une dynamique qui vise à s’inscrire dans la pérennité, au-delà du projet TIGA Lyon Saint-Etienne, pour devenir un laboratoire permanant de cocréation, de recherche-action et d’interactions entre les acteurs du territoire.
L’action 14 repose sur 4 démarches qui s’enrichissent mutuellement et se combinent autour d’un processus commun de production.

---

## Développement

### Py3DTiles

[Py3DTiles](https://github.com/VCityTeam/py3dtiles/tree/Tiler) est une librairie Python permettant de manipuler les [3D Tiles](https://github.com/CesiumGS/3d-tiles). Originellement développé par [Oslandia](https://gitlab.com/Oslandia/py3dtiles), cette bibliothèque a été enrichie et robustifiée au cours du projet TIGA.

Ajouts:

- Classes permettant de représenter les 3D Tiles en mémoire: Batch Table, Bounding Volume, Tile, Tileset.
- Mécanisme pour ajouter des extensions, ainsi que 2 extensions:
  - Batch Table Hierarchy: introduit la notion de hiérarchie et de typage dans la Batch Table.
  - Extension Temporelle: permet d'ajouter la temporalité dans un tileset.
- Validation de validation des 3D Tiles via schémas JSON.
- Matériaux glTF: permet de créer des matériaux texturés ou colorés.

Modifications:

- Modification de la classe Feature Table pour qu'elle soit utilisable par les 3D Tiles au format B3DM.
- Corrections de l'encodage/décodage des parties binaires des 3D Tiles au format B3DM.
- Faire en sorte que les 3D Tiles produits soient fidèles à la spécification.
- Amélioration de la lecture/écriture des 3D Tiles au format B3DM.

### Py3DTilers

[Py3DTilers](https://github.com/VCityTeam/py3dtilers) est un outil Python opn source permettant de créer des [3D Tiles](https://github.com/CesiumGS/3d-tiles) depuis différents formats: [OBJ](https://en.wikipedia.org/wiki/Wavefront_.obj_file), [GeoJSON](https://en.wikipedia.org/wiki/GeoJSON), [IFC](https://en.wikipedia.org/wiki/Industry_Foundation_Classes) et [CityGML](https://en.wikipedia.org/wiki/CityGML) (via une base de donnée [3dCityDB](https://3dcitydb-docs.readthedocs.io/en/release-v4.2.3/).

Py3DTilers utilise la librairie [Py3DTiles](#py3dtiles) pour sa représentation en mémoire des 3D Tiles.

Py3DTilers inclut des _Tilers_, permettant chacun de transformer un format précis de données en 3D Tiles. Ils sont au nombre de 5:

- [ObjTiler](https://github.com/VCityTeam/py3dtilers/tree/master/py3dtilers/ObjTiler#readme): converti des fichiers OBJ en 3D Tiles
- [GeojsonTiler](https://github.com/VCityTeam/py3dtilers/tree/master/py3dtilers/GeojsonTiler#readme): converti des fichiers GeoJSON en 3D Tiles
- [IfcTiler](https://github.com/VCityTeam/py3dtilers/tree/master/py3dtilers/IfcTiler#readme): converti des fichiers IFC en 3D Tiles
- [CityTiler](https://github.com/VCityTeam/py3dtilers/tree/master/py3dtilers/CityTiler#readme): converti des features CityGML (bâtiments, ponts, courts d'eau et relief) extraites d'un base 3DCityDB en 3D Tiles
- [TilesetReader](https://github.com/VCityTeam/py3dtilers/tree/master/py3dtilers/TilesetReader#readme): lit, fusionne et transforme des tilesets 3D Tiles déjà existant

Les Tilers partagent des [options communes](https://github.com/VCityTeam/py3dtilers/tree/master/py3dtilers/Common#common-tiler-features) pour personnaliser la création:

- La création de niveaux de détails
- La reprojection des données
- La translation et mise à l'échelle des modèles 3D
- L'export en modèle OBJ
- La création de 3D Tiles texturés ou colorés

### Démo Py3DTilers

- [Code](https://github.com/VCityTeam/UD-Demo-vcity-py3dtilers-lyon)
- [Docker](https://github.com/VCityTeam/UD-Demo-vcity-py3dtilers-lyon-docker)
- [Démo en ligne](https://py3dtilers-demo.vcityliris.data.alpha.grandlyon.com/)

Cette démo propose un ensemble de tilesets 3D Tiles créés avec les outils de Py3DTilers. On y retrouve des 3D Tiles de bâtiments, ponts, relief et cours d'eau, certains texturés et d'autres colorés.

### Démo UI-driven

- [Code](https://github.com/VCityTeam/UD-Demo-VCity-UI-driven-data-computation-Lyon)
- [Docker](https://github.com/VCityTeam/UD-Demo-VCity-UI-driven-data-computation-Lyon-docker)
- [Démo en ligne](https://ui-driven-data-lyon.vcityliris.data.alpha.grandlyon.com/)

Cette démo permet de calculer la hauteur de routes en les plaçant sur le relief. Pour cela, les routes doivent être contenues dans des fichiers GeoJSON. Ces fichiers peuvent ensuite être glissés/déposés. Les routes seront affichées au fur et à mesure du calcul. Une fois toutes les routes placées sur le relief, de nouveaux fichiers GeoJSON contenant les routes aux bonnes altitudes sont téléchargés.

![ezgif-5-42ca35522d](https://user-images.githubusercontent.com/32875283/165520908-eeda0798-4ca1-4e76-ad3c-6779d593cff3.gif)

### Autre

- "Couche de données WFS"
- "EpisodeVizualiser"
- [« Derrière les fumées »](https://github.com/VCityTeam/TIGA-Webdocumentaire/blob/main/README.md) : Web-documentaire interactif cherchant à acculturer l'habitant sur [la vallée de la chimie](https://fr.wikipedia.org/wiki/Vall%C3%A9e_de_la_chimie) et l'informer sur une thématique de ce territoire grâce à des interviews des acteurs de celui-ci.

---

## Documentations

- [Veille](https://docs.google.com/spreadsheets/d/1WMBi1XcP12ggSY--qWQrSYCXhRfvsycCfQJ3W6OuaC4/edit?usp=sharing) : Veille sur les outils de médiations lié au thème de l'industrie.
- [Mind map](https://docs.google.com/spreadsheets/d/1WMBi1XcP12ggSY--qWQrSYCXhRfvsycCfQJ3W6OuaC4/edit?usp=sharing) : "Min map" donnant une autre approche de visualisation de la veille.
- [Livrable 2020](./Livrables/Action14_UDL_LIRIS_2020.pdf) :
- Article Py3DTilers (en cours d'écriture) : Article de recherche sur Py3DTilers et ses fonctionnalités

### Documentation 3D Tiles

- [Visualisation des 3D Tiles](https://github.com/VCityTeam/UD-SV/blob/master/ImplementationKnowHow/Visualize3DTiles.md) : comment visualiser des 3D Tiles dans UD-Viz, iTowns et Cesium.
- [Créer des 3D Tiles depuis de l'open data](https://github.com/VCityTeam/UD-Reproducibility/blob/master/Computations/3DTiles/Lyon_Relief_Roads_Buildings_Water/Compute_Lyon_3DTiles.md) : créer des 3D Tiles de bâtiments, relief, cours d'eau, routes et ponts depuis l'open data du Grand Lyon et de l'IGN.

### Documentation PostGIS/3DCityDB

### Documentation calcul de données

- [Calcul d'altitude des routes](https://github.com/VCityTeam/UD-Reproducibility/blob/master/Computations/3DTiles/Lyon_Relief_Roads_Buildings_Water/Roads_from_relief.md) : Calculer les altitudes de routes (au format GeoJSON) à l'aide d'une [démo UD-Viz](#démo-ui-driven).

## Données

- [Photos de la catastrophe Feyzin](<https://numelyo.bm-lyon.fr/BML:BML_01ICO001015c33b77d0036c?&collection_pid=BML:BML_01ICO00101&luckyStrike=1&query[]=isubjectgeographic:%22Feyzin%20(Rh%C3%B4ne)%22&hitPageSize=1&hitTotal=62&hitStart=24>)
- [Modèle 3D de la métropole de Lyon](https://partage.liris.cnrs.fr/index.php/apps/files/?dir=/VCity/Data/Obj/Metropole%20de%20Lyon&fileid=251305282) : Données générées lors de projet étudiant de master en informatique.
- [Tilesets 3D Tiles de Lyon](https://dataset-dl.liris.cnrs.fr/three-d-tiles-lyon-metropolis/Demo/UD-Demo-vcity-py3dtilers-lyon/) : 3D Tiles générés avec Py3DTilers (bâtiments, relief, routes, ponts, fleuves)

### TO-DO

- Py3dtilers decouper avec la liste des socles de développement.
- Trouver un nom pour les développments techniques.
