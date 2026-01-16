# Tests API – Swagger Petstore (Postman)

## 📌 Objectif

Mettre en place une petite batterie de tests API automatisés sur l’API publique **Swagger Petstore** avec Postman, en couvrant un scénario complet :

1. Récupérer une liste d’animaux par statut  
2. Récupérer le détail d’un animal spécifique à partir de cette liste  
3. Créer un nouvel animal dédié aux tests  
4. Supprimer cet animal de test

Le tout en utilisant des **variables** et des **tests Postman**.

---

## 🛠️ Contenu du dossier

- `petstore-collection-pierre.json`  
  ➜ Collection Postman contenant les 4 requêtes suivantes :
  - `GET – Pets par statut`
  - `GET – Pet par id`
  - `POST – Créer un pet`
  - `DELETE – Supprimer newPet`

- `petstore-env-pierre.json`  
  ➜ Environnement Postman avec la variable :
  - `baseUrl = https://petstore.swagger.io/v2`

- `postman-run-petstore.png`  
  ➜ Capture d’écran de l’exécution de la collection dans Collection Runner avec tous les tests au vert ✅

---

## ▶️ Comment exécuter les tests

1. Importer `petstore-env-pierre.json` dans Postman  
2. Importer `petstore-collection-pierre.json` dans Postman  
3. Sélectionner l’environnement **“Petstore – Pierre Env”**  
4. Vérifier que la variable `baseUrl` est bien définie

### Exécution individuelle

- Lancer d’abord `GET – Pets par statut`  
  ➜ Récupère une liste de pets et stocke dynamiquement un `petId` dans les variables de collection  

- Puis lancer `GET – Pet par id`  
  ➜ Utilise `{{petId}}` pour vérifier que le pet retourné correspond bien à celui stocké

- Lancer `POST – Créer un pet`  
  ➜ Crée un nouvel animal avec un `id` fixe (`987654321`) et stocke `newPetId` pour la suppression

- Lancer `DELETE – Supprimer newPet`  
  ➜ Supprime le pet créé en utilisant `{{newPetId}}`

### Exécution via Collection Runner

1. Ouvrir la collection `Petstore – Pierre QA`
2. Cliquer sur **Run collection**
3. Sélectionner l’environnement **“Petstore – Pierre Env”**
4. Vérifier que les requêtes sont dans cet ordre :
   1. `GET – Pets par statut`
   2. `GET – Pet par id`
   3. `POST – Créer un pet`
   4. `DELETE – Supprimer newPet`
5. Cliquer sur **Run**

---

## 🧪 Scénario de test couvert

- Lecture de données (GET liste)  
- Lecture de détail (GET par id)  
- Création de ressource (POST)  
- Suppression de ressource (DELETE)  
- Chaînage des requêtes via variables (`petId`, `newPetId`)  
- Vérification du statut HTTP (`200`) et de la cohérence des données (id, message de suppression…)

---

## ✔️ Compétences démontrées

- Compréhension d’une API REST existante (Swagger Petstore)
- Configuration d’un environnement Postman (`baseUrl`)
- Création et organisation d’une collection de requêtes
- Utilisation de **variables de collection** et d’environnement
- Écriture de **tests Postman** en JavaScript (status code, structure de réponse, cohérence des IDs)
- Exécution de la collection via **Collection Runner** et interprétation des résultats

