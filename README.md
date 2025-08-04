# Celestial Bodies Database 🌌

Ce projet a été réalisé dans le cadre du cours **Relational Database Certification** de [FreeCodeCamp.org](https://www.freecodecamp.org/).  
Il consiste à créer une base de données relationnelle PostgreSQL contenant des informations sur les galaxies, étoiles, planètes et lunes.

## 🎯 Objectifs

- Créer une base de données nommée `universe`.
- Créer au moins 5 tables (`galaxie`, `etoile`, `planete`, `lune`, et `astronautes`) avec les types et contraintes spécifiés.
- Utiliser les types : `VARCHAR`, `INT`, `NUMERIC`, `TEXT`, `BOOLEAN`.
- Définir des relations entre les entités via des clés étrangères.
- Respecter les contraintes de nommage, d’unicité, de non-nullité et d’intégrité référentielle.

## 🛠️ Technologies

- PostgreSQL
- psql CLI (ligne de commande)
- SQL (création et manipulation de bases de données relationnelles)

## 🧱 Structure des tables

- `galaxie` : contient des galaxies avec description, distance, etc.
- `etoile` : chaque étoile appartient à une galaxie.
- `planete` : chaque planète tourne autour d’une étoile.
- `lune` : chaque lune orbite une planète.
- `astronautes` : table supplémentaire pour respecter la contrainte de 5 tables.

## 🔗 Relations

- `etoile.galaxy_id` → `galaxie.galaxy_id`
- `planete.star_id` → `etoile.star_id`
- `lune.planet_id` → `planete.planet_id`

## 📦 Dump SQL

Le fichier `universe.sql` contient le script complet de création et de peuplement de la base de données.  
Il peut être utilisé pour reconstruire la base en local :

```bash
psql -U postgres < universe.sql
```

Le fichier inclut :
- La création de la base `universe`
- La création des tables avec contraintes
- L’insertion de données (≥6 galaxies, ≥6 étoiles, ≥12 planètes, ≥20 lunes)

## 💡 Commande de sauvegarde utilisée

```bash
pg_dump -cC --inserts -U freecodecamp universe > universe.sql
```

## ✅ Tests requis FreeCodeCamp

Tous les tests du projet ont été validés :

- [x] Base `universe` créée
- [x] Clés primaires auto-incrémentées (`*_id`)
- [x] Types `INT`, `NUMERIC`, `TEXT`, `BOOLEAN`, `VARCHAR` utilisés correctement
- [x] Relations entre tables via clés étrangères
- [x] Contraintes de `NOT NULL` et `UNIQUE` respectées
- [x] Quantité minimale de lignes insérées
- [x] Noms des colonnes et conventions respectés

## 📁 Accès au fichier

> 🔗 [universe.sql](./universe.sql)

## 🚀 Auteur

- GitHub : [LEBONSON](https://github.com/LEBONSON)
- Projet réalisé pour la certification **Bases de données relationnelles** de FreeCodeCamp.
