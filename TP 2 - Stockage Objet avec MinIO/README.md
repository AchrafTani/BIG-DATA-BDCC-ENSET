# Rapport du TP 2 : Stockage Objet avec MinIO

**Module :** Big Data - Stockage objet  
**Objectif :** Mettre en place un service MinIO local, manipuler des fichiers de données et organiser leur stockage dans des buckets.

---

## 1. Présentation du TP

Ce travail pratique montre comment utiliser MinIO comme solution de stockage objet compatible avec l'API S3. L'environnement est lancé avec Docker Compose et permet de déposer, consulter et organiser différents fichiers de données.

Les fichiers utilisés dans ce TP sont :

- `ventes.csv` : données de ventes au format CSV ;
- `clients.json` : liste de clients au format JSON ;
- `produit.txt` : catalogue de produits au format texte ;
- `docker-compose.yaml` : configuration du serveur MinIO.

---

## 2. Lancement de MinIO

Le service MinIO est démarré à partir du fichier `docker-compose.yaml`.

```bash
docker compose up -d
```

Après le démarrage, l'interface web est disponible sur :

```text
http://localhost:9001
```

Les identifiants configurés sont :

```text
Utilisateur : minioadmin
Mot de passe : minioadmin123
```

---

## 3. Organisation des données

Une fois connecté à la console MinIO, un bucket peut être créé pour stocker les fichiers du TP. Les données locales sont ensuite importées dans ce bucket afin de simuler un espace de stockage objet.

Exemple d'organisation possible :

```text
tp2-minio/
|-- ventes.csv
|-- clients.json
`-- produit.txt
```

---

## 4. Vérification

La validation consiste à confirmer que les fichiers ont bien été ajoutés dans le bucket et qu'ils restent accessibles depuis l'interface MinIO.

Les points contrôlés sont :

- disponibilité du conteneur MinIO ;
- accès à la console web ;
- création du bucket ;
- import des fichiers de données ;
- consultation des objets stockés.

---

## Conclusion

Ce TP permet de découvrir le stockage objet avec MinIO et de comprendre son intérêt pour la gestion de fichiers dans un environnement Big Data. Les données sont centralisées dans un bucket et peuvent ensuite être utilisées par d'autres outils de traitement.
