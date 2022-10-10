## Derrière les fumées
« Derrière les fumées » est un jumeau digital du
[couloir de la chimie](https://fr.wikipedia.org/wiki/Vall%C3%A9e_de_la_chimie),
de l'unité urbaine de Lyon, qui invite à aller à la rencontre des familles et
des acteurs économiques et publics, qui vivent, se forment, et travaillent dans
la vallée.
Il désenchevêtre tous ces tuyaux entremêlés et donne du sens à ces produits
mystérieux qui sortent tous les jours de ces usines. A quoi cela peut servir ?
Où est-ce que je les rencontre au quotidien ? Pourquoi la plupart des maux de
tête du monde sont soignés grâce à la vallée de la chimie ? Au travers d’un
web documentaire gamifié et participatif, les acteurs du territoire, qu’ils
soient citoyens usagers ou habitants pourront se forger leur propre opinion,
participer au débat public et dissiper leur propre écran de fumée.
Ce jeu documentaire, dans lequel tout est réel, amène les participants,
au travers d’une enquête interactive, à confronter l’ensemble de leurs points
de vue pour mesurer les enjeux, l’engagement responsable de la vallée et
l’impact de ces usines sur nos vies au quotidien.
Pour entrer en « mode action », les spectateurs sont invités à voter, à
soumettre aux votes et aux avis des autres joueurs des actions concrètes pour faire évoluer les pratiques, pour mieux connaître le territoire, pour mieux se comprendre et ainsi devenir acteurs du territoire.

### Outils 
#### **Intégration de contenus multi-médias**
Afin d'améliorer la compréhension d'un territoire, nous voulions contextualiser les modèles 3D de bâtiments avec des données multi-médias additionnelles. Ces multi-médias peuvent être des images d'archives, des vidéos d'acteurs du territoire ou des photos d'un observatoire photographique(voir par exemple le travail sur l'[Observatoire photographique des paysages de la Vallée de la chimie](https://www.caue69.fr/1/page/10622/Observatoire_photographique_du_paysage_sur_le_territoire_de_la_Vallee_de_la_Chimie) mené par la mission vallée de la chimie. Ce nouveau contenu apporte une autre dimension à la déambulation dans un environnement 3D et l'améliore avec plus d'informations sur celui-ci. Nous avons donc développé une méthode d'intégration de multi-medias qui se base sur la libraire [UD-viz](https://github.com/VCityTeam/UD-Viz). L'intégration est découpée en deux parties :

- [Configuration du fichier JSON](https://github.com/VCityTeam/UD-Demo-TIGA-Webdoc-ChemistryValley/blob/main/doc/PinsDoc.md#configepisodesjson-) : documentation sur la configuration du fichier JSON afin de lier contenus multi-medias et positions géospatiales.
- [Episode visualizer object](https://github.com/VCityTeam/UD-Demo-TIGA-Webdoc-ChemistryValley/blob/main/doc/PinsDoc.md) : programme d'intégration des multi-médias avec comme point d'entrée le fichier de configuration JSON.


| ![contenue](https://user-images.githubusercontent.com/32339907/169073212-20ddc305-0926-4744-8424-6df0e0fe19e3.PNG) | 
|:--:| 
| *Figure 2 : "Derrière les fumées", intégration d'une interview de la directrice de la maison de l'emploi dans la représentation numérique de la vallée de la chimie* |

Ce socle technique est documenté dans la librairie UD-Viz ainsi que dans un article scientifique sur l'intégration de multi-média dans une représentation 3D numérique soumis à la même conférence internationale que Py3dTilers, [Smart Data Smart Cities & 3D GeoInfo](https://conference.unsw.edu.au/en/sdsc-3dgeoinfo) ([Article intégration de multimedia dans une représentation 3D numérique](https://github.com/VCityTeam/VCity/blob/master/articles/SDSC-Gautier-2022/main_commented.pdf)). Cet article a été accepté pour une présentation dans la conférence internationale [3DGeoinfo](https://conference.unsw.edu.au/en/sdsc-3dgeoinfo) et sera publié dans le journal international [ISPR Annals](https://www.isprs.org/publications/annals.aspx).

#### **Intégration de couches de données 2D**

Dans cette idée d'une meilleure compréhension, au-delà d'une représentation 3D, nous nous sommes intéressés à une visualisation 2D du territoire. En effet, les données 2D urbaines apportent une nouvelle vision sur un territoire et donnent plus d'informations sur celui-ci, comme l'accessibilité de certains quartiers grâce au réseau de transport en commun ou bien les zones végétalisées d'un arrondissement.

L'intégration de couches de données se fait via des services [WFS](https://www.geolittoral.developpement-durable.gouv.fr/IMG/pdf/note_explicative_wms_wfs_geolittoral.pdf) (Web Feature Service) et [WMS](https://www.geolittoral.developpement-durable.gouv.fr/IMG/pdf/note_explicative_wms_wfs_geolittoral.pdf) (Web Map service) dans la bibliothèque [UD-viz](https://github.com/VCityTeam/UD-Viz).
Ce type de données nous permet de représenter différentes géométries dans UD-Viz; cela peut être des polylignes, des polygones ou des images PNG/JPEG. Cet ajout de couches de données apporte une nouvelle vision à la représentation numérique et permet de contextualiser les modèles 3D de bâtiments.


| ![Capture](https://user-images.githubusercontent.com/32339907/169072790-425b4c26-053b-40fb-b5b3-771b9e34c315.PNG) | 
|:--:| 
| *Figure 3 : "Derrière les fumées": intégration de données urbaines 2D tel que lignes de transports en communs (lignes rouges) et les espaces naturels sensibles de la métropole de Lyon (polygones verts) dans la représentation numérique de la vallée de la chimie* |

A l'aide de ces socels techniques nous avons intégré le réseau de transport en commun pour montrer l'accessibilité à certains sites industriels de la vallée de la chimie. Nous avons également intégré les espaces naturels sensibles pour donner une autre vision de ce territoire.

### Partenaires
<p align="center">
  <img src="https://user-images.githubusercontent.com/32339907/194319619-48e4107b-be25-42b1-9850-f105db18ed87.png" alt="Home" height="100"/>
  <img src="https://user-images.githubusercontent.com/32339907/194319029-8604dea1-f00c-4880-9f83-50c9ed498e1d.png" alt="Home" height="90"/>
  <img src="https://user-images.githubusercontent.com/32339907/194319165-69368c5c-ac99-40b5-8089-5fac53a9e673.png" alt="Home" height="90"/>
</p>

### Références
- Lien vers le site en ligne du projet : https://www.derrierelesfumees.com/_Contenusdlf/Carte/index.html
- Veille des outils innovants : [lien](https://docs.google.com/spreadsheets/d/1WMBi1XcP12ggSY--qWQrSYCXhRfvsycCfQJ3W6OuaC4/edit#gid=0)
- Dépôts github open source:
  - [UD-Demo-TIGA-Webdoc-ChemistryValley](https://github.com/VCityTeam/UD-Demo-TIGA-Webdoc-ChemistryValley)
  - [UD-Demo-TIGA-Webdoc-ChemistryValley-Docker](https://github.com/VCityTeam/UD-Demo-TIGA-Webdoc-ChemistryValley-docker)
