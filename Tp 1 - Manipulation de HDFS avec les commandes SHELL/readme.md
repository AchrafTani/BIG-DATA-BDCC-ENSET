# Rapport de l'Exercice de Synthèse 21 : Pratique de HDFS

**Realise par :** Achraf  
**Encadre par :** Pr. Abdelmajid BOUSSELHAM 
**Module :** Big Data - Atelier Hadoop HDFS  
**Objectif :** Valider l'utilisation des principales commandes HDFS, notamment la création de répertoires, la gestion des fichiers, l'observation des blocs et le paramétrage de la réplication.

---

## 1. Réalisation des tâches (Étape par étape)

*Pré-requis : Les commandes ci-dessous sont lancées depuis le conteneur NameNode avec `docker compose exec namenode bash`.*

### Étape 1 & 2 : Mise en place de l'arborescence HDFS
Préparation du dossier principal ainsi que des répertoires `raw`, `archive` et `export`.
```bash
hdfs dfs -mkdir -p /exercice/raw /exercice/archive /exercice/export
```
