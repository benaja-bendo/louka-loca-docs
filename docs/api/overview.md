# API Louka-Loca - Vue d'ensemble

L'API Louka-Loca permet de gérer les utilisateurs, les biens immobiliers, les agences, et bien plus encore. 

## Base URL
http://localhost:8000/api/v1


## Endpoints principaux

| Ressource       | Méthode | Endpoint                | Description                                 |
|-----------------|---------|-------------------------|---------------------------------------------|
| Utilisateurs    | `GET`   | `/users`                | Liste des utilisateurs                      |
| Utilisateurs    | `POST`  | `/users/{id}/assign-role`| Assigner un rôle à un utilisateur           |
| Propriétés      | `GET`   | `/properties`           | Récupérer la liste des propriétés           |
| Agences         | `POST`  | `/agencies`             | Créer une nouvelle agence                   |
| Favoris         | `POST`  | `/favorites/{property_id}`| Ajouter un bien aux favoris                |

Exemple pour authentication.md dans docs/api :

# Authentification API

L'authentification utilise un système de token (API Laravel Sanctum ou Passport).

## Endpoint de connexion

- **URL** : `/login`
- **Méthode** : POST
- **Paramètres** :
  - `email` : L'adresse email de l'utilisateur
  - `password` : Le mot de passe de l'utilisateur

### Exemple de requête
```bash
curl -X POST http://localhost:8000/api/v1/login \
  -d 'email=john@example.com&password=secret'
```

### Exemple de réponse

```json
{
  "success": true,
  "message": "User authenticated successfully.",
  "data": {
    "token": "TOKEN",
    "user": {
      "id": 1,
      "name": "John Doe",
      "email": "john@example.com"
    }
  }
}
```

#### 2. **Guide d'installation (`installation.md`)**

Ce guide doit inclure les étapes nécessaires pour installer ton projet localement :

```markdown
# Installation de Louka-Loca

## Prérequis

- PHP >= 8.0
- Composer
- Node.js >= 14.x
- MySQL ou PostgreSQL

## Étapes d'installation

1. Clonez le repository :
   ```bash
   git clone https://github.com/votre-repo/louka-loca.git
   cd louka-loca