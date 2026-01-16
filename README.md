<p align="center">
  <img src="assets/Fooding_logo.png" alt="Fooding App Logo" width="180"/>
</p>

# Fooding Dataset 🍽️

Ce dépôt contient des fichiers de données au format JSON
regroupant des informations sur des restaurants situés
dans les villes de **Rabat** et **Tanger** (Maroc).

Ces données sont utilisées dans le cadre d’un projet académique
de recommandation de restaurants lié au **Mondial 2030**.

Le projet est **en cours d’évolution** et vise à intégrer
progressivement **l’ensemble des villes hôtes du Mondial 2030**.

---

## 📂 Structure des données

```text
data/
 ├── rabat.json    # Restaurants de la ville de Rabat
 └── tanger.json   # Restaurants de la ville de Tanger
docs/
 └── schema.json       # Schéma JSON des données restaurants
```

---

## 💾 Installation & Base de données MongoDB

### 1️⃣ Option 1 : MongoDB Compass (interface graphique)

1. Télécharge et installe **MongoDB Community Server** avec **MongoDB Compass** :  
[https://www.mongodb.com/try/download/community](https://www.mongodb.com/try/download/community)

2. Ouvre MongoDB Compass et connecte-toi à ton serveur local (`localhost:27017`).

3. Crée la base de données **Restaurants** et les collections :  
   - `Rabat`  
   - `Tanger`

4. Importer les fichiers JSON :  
   - Sélectionne la collection → **Add Data → Import File**  
   - Choisis le fichier JSON (`data/rabat.json` ou `data/tanger.json`)  
   - Format : **JSON Array** → Clique sur **Import**

---

### 2️⃣ Option 2 : mongosh (shell)

1. Installer le shell MongoDB :  
[https://www.mongodb.com/try/download/shell](https://www.mongodb.com/try/download/shell)

2. Vérifier l’installation :

```bash
mongosh --version
```
3. Lancer le shell :

```bash
mongosh
```
4. Créer la base de données et les collections :
   
```
use Restaurants
db.createCollection("Rabat")
db.createCollection("Tanger")
```
5. Importer les fichiers JSON depuis le terminal (optionnel) :

```
mongoimport --db Restaurants --collection Rabat --file data/rabat.json --jsonArray
mongoimport --db Restaurants --collection Tanger --file data/tanger.json --jsonArray
```

---

## 🧾 Schema JSON
Le fichier `docs/schema.json` décrit la structure et les types de toutes les données restaurants, et permet de valider les fichiers JSON avant de les importer dans MongoDB.

---

## 🎯 Objectif
- Construire un système de recommandation de restaurants
- Exploiter les données pour l’analyse, le filtrage et la recommandation
- Ajouter progressivement toutes les villes hôtes du Mondial 2030
