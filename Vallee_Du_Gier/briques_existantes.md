# Briques déjà existantes

Ce document regroupe toutes les briques développées en dehors du projet Vallée du Gier qui pourrait être réutilisées.

## Py3DTilers

Briques existantes dans le logiciel [Py3DTilers](https://github.com/VCityTeam/py3dtilers). Cet outil permet de transformer de la donnée géospatiale en modèles 3D au format [3D Tiles](https://github.com/CesiumGS/3d-tiles/tree/main/specification).

### Formats

Le logiciel peut créer des 3D Tiles à partir des formats suivants:

- OBJ
- IFC
- GeoJSON
- CityGML

Voir [usage](https://github.com/VCityTeam/py3dtilers#usage).

Voir [exemple](https://py3dtilers-demo.vcityliris.data.alpha.grandlyon.com/html/all_lyon.html).

![image](https://user-images.githubusercontent.com/32875283/189298423-ce904c9a-6ad0-4aee-95d4-564888d01a27.png)

### Texture

Il est possible de créer des modèles 3D Tiles texturés à partir des formats suivants:

- OBJ
- CityGML

Pour ces textures, il est possible de gérer de la qualité et la compression afin d'éviter d'obtenir des textures trop lourdes en mémoire.

Voir [usage](https://github.com/VCityTeam/py3dtilers/tree/master/py3dtilers/Common#with-texture).

Voir [exemple](https://py3dtilers-demo.vcityliris.data.alpha.grandlyon.com/html/textured.html).

![image](https://user-images.githubusercontent.com/32875283/189297589-a076d04f-1334-40ae-9f8b-2b7bc84c7718.png)

### Couleurs

Il est possible de créer des modèles colorés selon certaines modalités à partir des formats suivants:

- IFC
- GeoJSON
- CityGML

Pour le CityGML et l'IFC, les couleurs dépendent de la classe des différentes surfaces (par exemple un mur est blanc, un toit est rouge, etc). Pour le CityGML, l'utilisateur [peut personnaliser les couleurs](https://github.com/VCityTeam/py3dtilers/tree/master/py3dtilers/CityTiler#color) appliquées à chaque type de surface.

Pour le GeoJSON, l'utilisateur peut colorer les modèles 3D Tiles à partir de l'attribut GeoJSON de son choix. Il est par exemple possible de créer des [heat maps](https://fr.wikipedia.org/wiki/Heat_map) ou d'appliquer une couleur en fonction du type d'un bâtiment. Voir [usage](https://github.com/VCityTeam/py3dtilers/tree/master/py3dtilers/GeojsonTiler#color).

Voir [exemple](https://py3dtilers-demo.vcityliris.data.alpha.grandlyon.com/html/height_color.html).

![image](https://user-images.githubusercontent.com/32875283/189297922-20cc54cc-e1c8-4e51-a255-d573d248d7fa.png)

### Niveaux de détail

Il est possible de créer des modèles 3D Tiles avec plusieurs niveaux de détail depuis chacun des formats. Ces niveaux de détail permettent de réduire la précision des modèles lors de la visualisation et ainsi d'améliorer les performances quand beaucoup de modèles sont affichés.

Pour créer un LOA, voir [usage](https://github.com/VCityTeam/py3dtilers/tree/master/py3dtilers/Common#loa).

Pour créer un LOD1, voir [usage](https://github.com/VCityTeam/py3dtilers/tree/master/py3dtilers/Common#lod1).

Voir [exemple](https://py3dtilers-demo.vcityliris.data.alpha.grandlyon.com/html/all_lyon_lods.html).

![image](https://user-images.githubusercontent.com/32875283/189298146-d4415009-21f2-47e6-b8c1-eb56a53c4220.png)

### Transformations 3D

Il est possible de tranformer la donnée avant d'en faire des 3D Tiles. Les différentes opérations possibles sont:

- La translation: déplace les modèles sur les axes X,Y,Z
- Le changement d'échelle: grandit ou rétrécit la donnée selon un facteur
- La reprojection: change le système de projection (CRS) des données

Voir [usage](https://github.com/VCityTeam/py3dtilers/tree/master/py3dtilers/Common#3d-transformations).

### Extension temporelle

## UD-Viz

Briques existantes dans le logiciel [UD-Viz](https://github.com/VCityTeam/UD-Viz). UD-Viz permet de visualiser des données géospatiales via navigateur Web, en plus de proposer des outils pour intéragir avec cette donnée. UD-Viz est basé sur la bibliothèque [iTowns](https://github.com/iTowns/itowns) développé par l'IGN.

### Elévation et fond de carte

Il est possible dans UD-Viz de charger et d'afficher des flux WMS et WFS afin d'obtenir des fonds de carte et des élévations.

Pour un fond de carte, il est possible de choisir le nombre maximum de subdivision. Exemple:

```json
  "background_image_layer": {
    "url": "https://wxs.ign.fr/choisirgeoportail/geoportail/r/wms",
    "name": "GEOGRAPHICALGRIDSYSTEMS.PLANIGNV2",
    "version": "1.3.0",
    "format": "image/jpeg",
    "layer_name": "Base_Map",
    "maxSubdivisionLevel": 5
  }
```

Pour une élévation, il est possible de choisir à quelles hauteurs correspondent le miminum et le maximum du flux d'entrée. Cela permet de modifier facilement la hauteur des élévations. Exemple:

```json
  "elevation_layer": {
    "url": "https://download.data.grandlyon.com/wms/grandlyon",
    "name": "MNT2018_Altitude_2m",
    "format": "image/jpeg",
    "layer_name": "wms_elevation_test",
    "colorTextureElevationMinZ": 149,
    "colorTextureElevationMaxZ": 628
  }
```

### Chargement de couches 3D Tiles

Des objets 3D urbains peuvent être chargés dans UD-Viz sous forme de couches 3D Tiles. Ces 3D Tiles peuvent être des nuages de points (Point Clouds) ou des modèles 3D maillés au format B3DM (Batched 3D Models).

Pour les Point Clouds, il est possible de choisir la taille des points. Exemple:

```json
  "3DTilesLayers": [
    {
      "id": "Point-Cloud",
      "url": "https://dataset-dl.liris.cnrs.fr/three-d-tiles-lyon-metropolis/2018/Point_Cloud_Lyon_2018/tileset.json",
      "pc_size": 2
    }
  ]
```

Pour les B3DM, il est possible de choisir une couleur qui sera appliqué à l'ensemble des modèles 3D de la couche. Si aucune couleur n'est indiqué, les couleurs utilisées sont celles déjà présentes dans les modèles 3D. Exemple:

```json
  "3DTilesLayers": [
    {
      "id": "3d-tiles-layer-building",
      "url": "https://dataset-dl.liris.cnrs.fr/three-d-tiles-lyon-metropolis/2018/Lyon_2018/tileset.json"
    },
    {
      "id": "3d-tiles-layer-relief",
      "url": "https://dataset-dl.liris.cnrs.fr/three-d-tiles-lyon-metropolis/Demo/UD-Demo-vcity-py3dtilers-lyon/Lyon_2018_Relief_TileSet/tileset.json",
      "color": "0xd0ac7f"
    }
  ]
```

### Chargement de couches GeoJSON

### Widget CityObject

Le widget CityObject intègre plusieurs fonctionnalités:

- Sélectionner un objet 3D de la scène. Cela applique une couleur à l'objet.
- Afficher les attributs de l'objet sélectionné.
- Zoomer sur l'objet grâce au bouton `Focus`.
- Filtrer les objets de la objets de la scène grâce au bouton `Filter`.

Voir [exemple](https://ud-viz.vcityliris.data.alpha.grandlyon.com/examples/CityObjectWidget/example.html).

![image](https://user-images.githubusercontent.com/32875283/189299959-744c3314-c64f-4827-9084-dd233bd22250.png)

### Widget Document

Le widget Document permet de visualiser des documents placés à des positions géographiques.

![image](https://user-images.githubusercontent.com/32875283/195586644-19173c1a-253f-449e-b42a-e301c2ace025.png)

### Widget Slideshow

![image](https://user-images.githubusercontent.com/32875283/195586732-43771017-e83b-4482-a387-12492d780300.png)

### Widget LayerChoice

Le widget LayerCHoice permet de cacher/afficher les couches de données (géométriques ou fonds de carte). Il est également possible de focus la caméra sur une couche 3D.

![image](https://user-images.githubusercontent.com/32875283/195586360-5598fd98-ea88-4335-84be-47ee98ed886d.png)

### Billboard
