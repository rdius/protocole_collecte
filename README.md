## Protocole de collecte de données textuelles pour la constitution de corpus thématiques 

![alt tag](./protocole_sageo.png)

Ce protocole permet de constituer des corpus thématiques ancrés sur le plan spatio-temporel :

  * construire un corpus en specifiant le nom de la thématique et le nom de la ville, de la commune ou du territoire concerné
  * récupération autmatique de métadonnées pour chaque document tellesque :
      * la date de publication
      * le titre
      * les Entités Nommées Spatiales
      * la pertinence du document vis-à-vis de la thématique
      * l'url
      * le contenu du document
      * Etc.

## Constitution des corpus thématiques

* un  vocabulaire de concepts est utilisé pour collecter des documents sur Google et former ainsi de gros corpus thématiques.

* Pour s'assurer de la qualité des contenus des documents que nous collectons, nous avons mis en place une évaluation automatisée, basée sur la mesure de similarité proposée précédement avec DistilBert. Cette mesure de similarité est faite pour chaque  document collecté, avec le vocabulaire de concepts étendus. Pourquoi un vocabulaire de concepts étendus ? Nous proposons d'utiliser un vocabulaire de concepts étendus pour chaque thématique lors de la collecte, dans le but de pouvoir prendre en compte les documents de nature sociétale, dont le contenu contient un language moins soutenu (orienté société ou language de la majorité), généralement en provenance des forums blogs etc. Le vocabulaire de concepts étendus est obtenu en génerant pour chaque terme du vocabulaire initial, des synonymes en utilisant WordNet.

* Les documents obetenus, avec leur score de similarité sont ainsi classés par ordre décroissant, les scores les plus élevés correspondent aux documents les plus pertinents vis-à-vis de leur contenu. 


### Thematic Concepts Vocabulary for test in  ./voc_concepts

```
pip install -r requirements.txt

# Change the voc_concept_file and the spatial_extent to your own.

voc_concept_file =  "./voc_concept/agriculture.txt" 
spatial_extent = 'montpellier'
advanced_scraper(spatial_extent,voc_concept_file,voc_concept_file)
```
