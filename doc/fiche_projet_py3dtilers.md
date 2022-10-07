# Py3DTilers : un outil pour manipuler et transformer de la donnée geospatiale

Les données urbaines et géospatiales sont de plus en plus utilisées dans la création de doubles numériques de la ville. L'utilisation de ces doubles numériques pose un problème majeur: la très grande quantité d'informations (milliers de bâtiments, relief complexe, etc) rend difficile de manipuler et visualiser ces données en temps réel. Le format [3D Tiles](https://www.ogc.org/standards/3DTiles) a été créé en 2015 dans le but de résoudre ce problème. Les 3D Tiles sont découpés spatialement en **tuiles**, c'est-à-dire que les données sont réparties dans des sous-ensembles en fonction de leur position dans l'espace. Cette répartition permet de ne charger que certaines parties des données, celles dans le champs de vision de l'utilisateur, lors de la déambulation dans la maquette numérique.

[Py3DTilers](https://github.com/VCityTeam/py3dtilers) est un outil libre développé dans le cadre du projet TIGA. Il permet de créer des 3D Tiles depuis différents formats de données: [OBJ](https://en.wikipedia.org/wiki/Wavefront_.obj_file), [GeoJSON](https://en.wikipedia.org/wiki/GeoJSON), [IFC](https://en.wikipedia.org/wiki/Industry_Foundation_Classes) et [CityGML](https://en.wikipedia.org/wiki/CityGML). Ces formats de données sont utilisés pour représenter des données géographiques et urbaines, 2D ou 3D, telles que les bâtiments, le relief, les routes ou le mobilier urbain.

## Outils et innovation

Py3DTilers se veut être le premier outil open source pour créer et manipuler des 3D Tiles. Il se différencie des autres outils de création de 3D Tiles par le grand nombre d'options et paramètres dont il dispose, ainsi que par la liberté totale qu'il offre sur le processus de création. L'objectif de Py3DTilers est de proposer à la communauté un outil permettant de tester et d'innover autour du format 3D Tiles.

### Fonctionnalités de Py3DTilers

Py3DTilers offre un grand nombre d'options permettant d'adapter les 3D Tiles produits aux besoins de l'utilisateur. Les principales fonctionnalités proposées sont :

- **La création de niveaux de détails**: permet d'ajouter un ou plusieurs [niveaux de détail](https://fr.wikipedia.org/wiki/Level_of_detail) aux géométries. Cela permet de fluidifier la visualisation en affichant des modèles 3D plus ou moins détaillés.

<img width="400" alt="lod2" src="https://user-images.githubusercontent.com/32875283/194566234-2f73884e-c496-45d8-b5e1-1b3f82414ee3.png"><img width="400" alt="lod1" src="https://user-images.githubusercontent.com/32875283/194566265-4cc473c4-6e69-4239-98d0-9997f8d71f55.png">

- **La transformation des données 3D**: permet de modifier la donnée en la reprojetant ou en changeant l'échelle et la position des géométries. Cela permet de placer les données dans le contexte 3D voulu ou encore de corriger les erreurs de placement et de taille des objets dans la scène. Ces fonctionnalités permettent aussi de placer de la donnée non géo-référencée dans un contexte géospatial, ou inversement de placer de la donnée géo-référencée à des coordonnées centrées autour de (0, 0, 0).

<img width="400" alt="offset_1" src="https://user-images.githubusercontent.com/32875283/194566134-33f70dd4-e23c-4651-b40c-53621b22302d.png"><img width="400" alt="offset_2" src="https://user-images.githubusercontent.com/32875283/194566168-abeff148-e861-44d7-8032-1ee735657cff.png">

- **L'ajout de textures**: si la donnée d'entrée est texturée, l'utilisateur peut choisir de conserver ou non les textures. Lorsque les textures sont conservées, elles sont stockées dans des atlas de textures sous forme de fichiers JPEG.

<img width="800" alt="city_tiler_texture" src="https://user-images.githubusercontent.com/32875283/194566052-4c8893ce-5ae3-4efc-8381-f900e685be88.png">

- **La création de 3D Tiles colorés**: permet d'ajouter des couleurs aux 3D Tiles. Les couleurs peuvent être choisies par l'utilisateur. Les couleurs peuvent être appliquées en fonction d'attributs des modèles (par exemple hauteur du bâtiment) ou en fonction du type des objets (toit, mur, sol, etc).

<img width="800" alt="city_tiler_colors" src="https://user-images.githubusercontent.com/32875283/194565899-e071979d-a0b6-4098-8b13-27efecde3d57.png">

### Démonstration des fonctionnalités

Une démonstration est [disponible en ligne](https://py3dtilers-demo.vcityliris.data.alpha.grandlyon.com/) afin d'illustrer plusieurs jeux de données 3D Tiles produits avec Py3DTilers.

<img width="800" alt="demo_py3dtilers" src="https://user-images.githubusercontent.com/32875283/194566826-76b5b631-ff05-46d4-8b33-cb2f69040a63.png">

Py3DTilers est également utilisé dans d'autres projets pour la production de modèles 3D, par exemple dans le web documentaire ["_Derrière les fumées_"](https://github.com/VCityTeam/TIGA/blob/master/doc/fiche_projet_Derriere_les_fumees.md) ou le campus virtuel ["_IMUV - Flying Campus_"](https://www.imuvirtuel.fr/).

## Partenaires

Le projet Py3DTilers a été effectué au sein du projet TIGA, financé par La Banque des Territoires, avec la collaboration du LabEx IMU, du laboratoire de recherche Liris et de l'entreprise Berger-Levrault.

<img width="300" src="https://user-images.githubusercontent.com/32875283/194567103-809c7e2d-b06c-4737-a9dd-daf31dad6876.png"><img width="300" src="https://user-images.githubusercontent.com/32875283/194567231-3550f0db-b7e4-4d54-b94c-3c50ef57bddf.png">    <img width="300" src="https://user-images.githubusercontent.com/32875283/194568572-182fd908-43e9-476d-893c-e449dd74214a.png">

## Références

- Code et documentation de Py3DTilers : [GitHub](https://github.com/VCityTeam/py3dtilers)
- Code et documentation de la Démonstration en ligne : [GitHub](https://github.com/VCityTeam/UD-Demo-vcity-py3dtilers-lyon)
- Article de recherche présenté à la conférence 3DGeoInfo : [PDF](https://github.com/VCityTeam/TIGA/blob/master/doc/article_py3dtilers.pdf)
- Livrable 2022 présentant les développements TIGA : [PDF](https://github.com/VCityTeam/TIGA/blob/master/doc/livrable2022.pdf)
