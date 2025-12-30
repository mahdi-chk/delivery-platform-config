# ⚙️ Delivery Platform Config

## 📌 Description

Le dépôt **delivery-platform-config** contient la **configuration centralisée** de tous les microservices du projet **Delivery Platform**.

Il est utilisé avec **Spring Cloud Config Server** afin de :

* Centraliser les fichiers de configuration
* Éviter la duplication des paramètres
* Faciliter la maintenance et les mises à jour
* Gérer les configurations par service

---

## 🧱 Rôle dans l’Architecture

Ce dépôt est consommé par un **Config Server** qui fournit dynamiquement les paramètres aux microservices.

```
Microservice ───► Config Server ───► delivery-platform-config
```

Chaque microservice charge sa configuration au démarrage depuis ce dépôt.

---

## 📂 Structure du Dépôt

```
delivery-platform-config/
│
├── application.properties
├── eureka-server.properties
├── gateway-server.properties
├── delivery-api.properties
├── restaurant-service.properties
├── commande-livraison-service.properties
└── README.md
```

---

## 📄 Description des Fichiers

### 🔹 `application.properties`

Configuration globale partagée entre tous les microservices (ex : ports communs, logs, paramètres généraux).

### 🔹 `eureka-server.properties`

Configuration spécifique au **Eureka Server** :

* Port du serveur
* Nom de l’application
* Paramètres de registre de services

### 🔹 `gateway-server.properties`

Configuration de l’**API Gateway** :

* Routage des requêtes
* Découverte des services
* Filtres

### 🔹 `delivery-api.properties`

Configuration du service **delivery-api** :

* Port
* Connexion aux autres services
* Paramètres métier

### 🔹 `restaurant-service.properties`

Configuration du service **restaurant-service** :

* Paramètres REST
* Accès aux données

### 🔹 `commande-livraison-service.properties`

Configuration du service **commande-livraison-service** :

* Gestion des commandes
* Gestion des livraisons

---

## 🔐 Bonnes Pratiques

* ❌ Ne pas stocker de mots de passe sensibles en clair
* ✔️ Utiliser des variables d’environnement si nécessaire
* ✔️ Séparer les configurations par service
* ✔️ Centraliser les paramètres communs dans `application.properties`

---

## ▶️ Utilisation avec Spring Cloud Config

1. Lancer le **Config Server**
2. Le Config Server pointe vers ce dépôt Git
3. Chaque microservice récupère sa configuration automatiquement

Exemple (dans `bootstrap.properties`) :

```properties
spring.application.name=restaurant-service
spring.config.import=optional:configserver:http://localhost:8888
```

---

## 🎯 Objectifs Pédagogiques

* Comprendre la configuration centralisée
* Appliquer Spring Cloud Config
* Simplifier la gestion des microservices
* Améliorer la maintenabilité du projet

---

## 👨‍💻 Auteur

* **ElMahdi Chakouch**
* **Younes Sadoq**
* **Yahya Benmadane**
---

## 📄 Licence

Projet à usage **éducatif**.

---

⭐ *Ce dépôt complète le projet delivery-platform.*
