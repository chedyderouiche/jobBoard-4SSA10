# Bibliothèque universitaire – Projet AWD (4SSA10, ESPRIT)

Plateforme de gestion d'une bibliothèque universitaire en **architecture microservices** : catalogue de livres, emprunts, amendes, utilisateurs, réservations et notifications.

> Validation intermédiaire (semaine 4) : la conception est terminée. Le développement des microservices commence maintenant.

## Équipe et répartition des tâches

Chaque membre développe d'abord seul son microservice (CRUD, base de données, contrat d'API, diagrammes). Ensuite, toute l'équipe travaille ensemble sur les parties communes.

| Membre | Travail individuel | Base de données |
|--------|--------------------|-----------------|
| Chayma | Microservice Livres (`/api/books`) | MongoDB |
| Fatma | Microservice Emprunts (`/api/loans`) | PostgreSQL |
| Chedy | Microservice Amendes (`/api/fines`) | PostgreSQL |
| Rayen | Microservice Utilisateurs (`/api/users`) | MySQL |
| Itaf | Microservice Réservations (`/api/reservations`) | Redis |

**Travail d'équipe :** conception, Eureka, API Gateway, OpenFeign, RabbitMQ, sécurité JWT, microservice commun Notifications, frontend Angular, tests, dossier technique et présentation.

## Architecture

- **Frontend** : Angular
- **API Gateway** : Spring Cloud Gateway (point d'entrée unique, vérification du JWT)
- **Découverte de services** : Eureka
- **Communication synchrone** : OpenFeign (REST)
- **Communication asynchrone** : RabbitMQ, avec les événements `LOAN_CREATED`, `BOOK_RETURNED`, `LOAN_OVERDUE`, `BOOK_ADDED`, `USER_CREATED`, `FINE_CREATED` et `BOOK_AVAILABLE_FOR_RESERVATION`
- **Sécurité** : Spring Security + JWT (rôles ETUDIANT, BIBLIOTHECAIRE, ADMIN)
- **Documentation des API** : OpenAPI / Swagger
- **Backend** : Spring Boot (Java 17), une base de données par service

Le schéma complet se trouve dans `Documentation/Diagrams/`.

## Structure du dépôt

```
├── Backend/            microservices Spring Boot (un dossier par service)
├── Frontend/           application Angular
├── Documentation/
│   ├── Presentation/   présentation de la validation
│   ├── Diagrams/       architecture, cas d'utilisation, classes, séquences
│   └── Document technique (PDF)
└── README.md
```

## Organisation Git

- `main` : version stable, sans commit direct
- `feature/<tâche>` : une branche par tâche (exemple : `feature/loan-service-crud`)
- Chaque branche est intégrée dans `main` par une **pull request** relue par un autre membre.
- Suivi des tâches dans **GitHub Projects** (Kanban : À faire / En cours / Terminé).

## Planning

| Phase | Travail | Objectif |
|-------|---------|----------|
| Phase 1 (séance 4) ✅ | Équipe | Conception : architecture, microservices, contrats d'API, dépôt Git |
| Phase 2 | Individuel | CRUD de chaque microservice et de sa base de données |
| Phase 3 | Équipe | Eureka, API Gateway, OpenFeign |
| Phase 4 | Équipe | RabbitMQ, service Notifications, sécurité JWT |
| Phase 5 | Équipe | Frontend Angular, tests, validation finale |
