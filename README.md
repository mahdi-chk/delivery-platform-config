# Delivery Platform - Configuration Repository

Ce dépôt contient toutes les configurations centralisées pour la plateforme de livraison.

## Structure
```
config/
├── application.properties              # Configuration commune
├── eureka-server.properties
├── gateway-server.properties
├── restaurant-service.properties
├── commande-livraison-service.properties
└── delivery-api.properties
```

## Format

Toutes les configurations utilisent le format `.properties` au lieu de `.yml`.

## Modification

1. Modifier le fichier de configuration
2. Commit et push sur GitHub
3. Les services récupèrent automatiquement les nouvelles configurations

## Variable obligatoire

**commande-livraison-service.properties** contient la variable requise:
```properties
mes-config-ms.commandes-last=10
```

Cette variable définit le nombre de jours pour afficher les dernières commandes.