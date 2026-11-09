# Bibliothèque universitaire – Plateforme de gestion en microservices

## 1. Présentation du projet

Cette plateforme web permet de gérer une bibliothèque universitaire sans registres papier.

Elle permet aux bibliothécaires de gérer le catalogue, les emprunts et les amendes, et aux étudiants de rechercher des livres, de les emprunter et de suivre leurs emprunts en ligne.

## 2. Objectifs du projet

- Remplacer la gestion manuelle des emprunts et des retours.
- Connaître en temps réel la disponibilité des livres.
- Suivre automatiquement les retards et calculer les amendes.
- Prévenir les étudiants (confirmation d'emprunt, rappel de retour).

## 3. Fonctionnalités principales

### Côté étudiant
- Créer un compte et se connecter.
- Consulter et rechercher les livres.
- Emprunter un livre disponible.
- Retourner un livre.
- Suivre ses emprunts et ses amendes.

### Côté bibliothécaire
- Ajouter, modifier et supprimer des livres.
- Gérer les utilisateurs.
- Suivre les emprunts en cours et les retards.
- Gérer les amendes.

### Côté administrateur
- Gérer les comptes des bibliothécaires.
- Superviser la plateforme.

## 4. Microservices

| Service | Rôle | Base de données | Responsable |
|---|---|---|---|
| book-service | Catalogue et disponibilité des livres | [BD] | [Nom] |
| user-service | Comptes étudiants et bibliothécaires | [BD] | [Nom] |
| loan-service | Emprunts et retours | PostgreSQL | Fatma Chelbi |
| fine-service | Amendes et pénalités | [BD] | [Nom] |
| notification-service | Notifications (service commun) | — | Toute l'équipe |

## 5. Structure du projet

```text
bibliotheque-4SSA10/
│
├── Backend/          # Microservices, API Gateway, Eureka
├── Frontend/         # Interface utilisateur
├── Documentation/    # Présentation, diagrammes, dossier technique
└── README.md         # Présentation du projet
```

## 6. Technologies utilisées

Les technologies utilisées seront précisées selon les choix techniques du projet.

## 7. Installation et lancement

Les instructions d'installation et de lancement seront ajoutées après la configuration du Backend et du Frontend.

## 8. Équipe du projet

Projet réalisé dans le cadre d'un travail académique en équipe (4SSA10).

## 9. Statut du projet

En cours de conception.
