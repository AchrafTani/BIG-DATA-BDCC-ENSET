# Big Data - Travaux Pratiques

**Realise par :** Achraf  
**Encadre par :** Pr. Abdelmajid BOUSSELHAM  
**Etablissement :** ENSET Mohammedia  
**Filiere :** MII-BDCC  
**Annee scolaire :** 2025-2026

---

## Vue d'ensemble

Ce depot rassemble une serie de travaux pratiques consacres aux principaux outils de l'ecosysteme Big Data. Les projets couvrent l'analyse batch avec Spark SQL, le traitement de flux avec Spark Structured Streaming et Kafka Streams, ainsi que l'orchestration de pipelines avec Apache Airflow.

Chaque dossier correspond a un atelier independant avec son code source, sa configuration Docker, ses donnees d'exemple et ses captures de validation.

---

## Organisation du depot

```text
BIG-DATA-BOUSSELHAM-MII-BDCC-ENSET-main/
|-- TP 3 - SPARK SQL/
|-- TP 4 - Analyse en temps quasi reel des mesures de capteurs avec Spark Structured Streaming et HDFS/
|-- TP 5 - Traitement de flux avec Kafka Streams/
`-- TP 6 - Atelier Big Data Apache Airflow pour l'orchestration des pipelines Big Data/
```

---

## TP 3 - Spark SQL

Ce TP met en place une application Java basee sur Apache Spark SQL pour analyser un fichier CSV contenant **5 000 locations de velos**.

Les traitements realises portent sur :

- le chargement et l'exploration d'un dataset CSV ;
- la creation d'une vue temporaire SQL ;
- l'execution de requetes d'agregation ;
- l'analyse des stations, des horaires et des profils utilisateurs.

**Technologies utilisees :** Apache Spark, Java 17, Maven, Docker.

Quelques resultats obtenus :

| Indicateur | Valeur |
|---|---|
| Nombre total de locations | 5 000 |
| Revenu total | 41 755.7 MAD |
| Station la plus active | Station Hopital |
| Heure de pointe | 19h |
| Age moyen | 41.5 ans |

---

## TP 4 - PySpark Structured Streaming et HDFS

Ce projet illustre le traitement de donnees de capteurs en quasi temps reel avec PySpark Structured Streaming. Les fichiers CSV sont injectes dans HDFS puis traites progressivement par Spark.

Le pipeline permet de :

- lire des donnees en streaming depuis HDFS ;
- calculer des statistiques par capteur ;
- detecter les valeurs anormales ;
- utiliser des checkpoints HDFS pour assurer la reprise apres interruption.

**Technologies utilisees :** PySpark, Apache Spark, Hadoop HDFS, YARN, Docker Compose.

Schema simplifie du flux :

```text
CSV locaux -> HDFS -> Spark Structured Streaming -> Statistiques + Alertes
```

---

## TP 5 - Kafka Streams

Ce TP est consacre au traitement de flux avec Apache Kafka Streams. Il contient trois exercices complementaires permettant de manipuler des messages en temps reel.

Les exercices realises sont :

| Exercice | Description |
|---|---|
| Text Cleaner | Nettoyage, validation et routage de messages texte |
| Weather Analyzer | Analyse de donnees meteo et exposition de metriques Prometheus |
| Click Stream Analytics | Comptage de clics avec Spring Boot, Kafka Streams et API REST |

**Technologies utilisees :** Apache Kafka, Kafka Streams, Java, Spring Boot, Maven, Docker, Prometheus.

---

## TP 6 - Apache Airflow

Le dernier atelier porte sur l'orchestration de pipelines Big Data avec Apache Airflow. L'environnement est deploye avec Docker Compose et plusieurs DAGs Python sont implementes.

Les notions pratiquees incluent :

- la creation de DAGs ;
- l'utilisation de `PythonOperator` ;
- l'enchainement sequentiel de taches ;
- l'execution parallele ;
- la consultation des logs ;
- la planification automatique ;
- la gestion des erreurs et des retries.

**Technologies utilisees :** Apache Airflow, Python, Docker Compose, PostgreSQL.

---

## Technologies couvertes

| Technologie | Utilisation principale |
|---|---|
| Apache Spark SQL | Analyse batch de donnees structurees |
| PySpark Structured Streaming | Traitement de flux en micro-batch |
| Hadoop HDFS | Stockage distribue des fichiers |
| YARN | Gestion des ressources du cluster |
| Apache Kafka | Messagerie distribuee |
| Kafka Streams | Traitement de flux applicatif |
| Spring Boot | Applications producer, consumer et API REST |
| Prometheus | Exposition de metriques |
| Apache Airflow | Orchestration de workflows |
| Docker / Docker Compose | Deploiement des environnements |

---

## Execution generale

Chaque TP dispose de son propre README avec les commandes adaptees. En general, les etapes suivent ce schema :

```bash
docker compose up -d
```

Puis, selon le TP :

- compilation Maven pour les projets Java ;
- soumission Spark avec `spark-submit` ;
- execution des applications Kafka Streams ;
- lancement et supervision des DAGs Airflow.

---

## Conclusion

L'ensemble du depot presente une progression pratique autour des architectures Big Data modernes : analyse batch, streaming, stockage distribue, messagerie evenementielle et orchestration. Les differents ateliers montrent comment ces outils peuvent etre combines pour construire des pipelines de donnees complets, observables et reproductibles.
