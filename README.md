# Angular Assignement Project 

Projet angular réalisé par Avramov Johann et Guillou Quentin

  - [Présentation vidéo](https://youtu.be/pM0MHkQkOo4)

  - [Lien du back](https://projet-angular-back.onrender.com/)

  - [Lien du front](https://project-angular-assignment.onrender.com)
## Travailler effectué

__Guillou Quentin__
  - améliorer forms
  - rendu ne peut pas être modifié si il n'y a pas de note
  - Améliorer l'affichage des Assignments
  - Ajouter de nouvelles propriétés au modèle des Assignments
  - Peupler BDD


__Johann avramov__
  - Amélioration supplémentaire
  - Adapté les nouvelles propriétés des assignments au front
  - Ajouter une gestion de login/password
  - Ajout snackBar
  - Design du site
  - Création gestion utilisateur profile : Teacher/Student


## Installation

### Etape 1 
Cloner le projet

### Etape 2 

Lancer la commande suivant dans le dossier front et back:

```bash
  npm install
```

### Etape 3 

Dans le dossier front excéuter:

```bash
  ng serve
```

### Etape 4 

DAns le dossier back excéuter:

```bash
  nodemon server
```## Acknowledgements

 - [https://readme.so](https://readme.so/fr/editor)
 - [Vidéo de présentation du site](https://github.com/matiassingers/awesome-readme)


## Reference API

### Professeur

#### Enregistrer un nouveau professeur

```http
  POST /api/teacher/register
```

| Body | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `email` | `string` | **Required**. Un email |
| `picture` | `URL` | **Required**. Url d'une image |
| `username` | `string` | **Required**. Un pseudo |
| `nom` | `string` | **Required**. Un nom |
| `prenom` | `string` | **Required**. Un prenom |
| `password` | `string` | **Required**. Un mot de passe |

#### Connexion en temps que professeur

```http
  POST /api/teacher/login
```

| Body | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `username` | `string` | **Required**. Un pseudo |
| `password` | `string` | **Required**. Un mot de passe |

#### Récupérer un professeur par id

```http
  GET /api/teacher/:id
```
| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `id` | `string` | **Required**. id du professeur recherché |


#### Récupérer un professeur par sont jwt token

```http
  POST /api/teacher
```
| Body | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `token` | `string` | **Required**. jwt tokebn du professeur recherché |

```http
  POST /api/teacher/update
```
| Body | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `email` | `string` | **Optionel**. Un email |
| `picture` | `URL` | **Optionel**. Url d'une image |
| `username` | `string` | **Optionel**. Un pseudo |
| `nom` | `string` | **Optionel**. Un nom |
| `prenom` | `string` | **Optionel**. Un prenom |
| `password` | `string` | **Optionel**. Un mot de passe |


### Elève

#### Enregistrer un nouveau elève

```http
  POST /api/student/register
```

| Body | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `email` | `string` | **Required**. Un email |
| `username` | `string` | **Required**. Un pseudo |
| `nom` | `string` | **Required**. Un nom |
| `prenom` | `string` | **Required**. Un prenom |
| `password` | `string` | **Required**. Un mot de passe |

#### Connexion en temps qu'élève

```http
  POST /api/student/login
```

| Body | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `username` | `string` | **Required**. Un pseudo |
| `password` | `string` | **Required**. Un mot de passe |

#### Récupérer un élève par id

```http
  GET /api/student/:id
```
| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `id` | `string` | **Required**. id de l'élève recherché |


#### Récupérer un élève par sont jwt token

```http
  POST /api/student
```
| Body | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `token` | `string` | **Required**. jwt tokebn de l'élève recherché |

```http
  POST /api/student/update
```
| Body | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `email` | `string` | **Optionel**. Un email |
| `username` | `string` | **Optionel**. Un pseudo |
| `nom` | `string` | **Optionel**. Un nom |
| `prenom` | `string` | **Optionel**. Un prenom |
| `password` | `string` | **Optionel**. Un mot de passe |

### Assignement

#### Enregistrer un nouvelle assignment

```http
  POST /api/assignments
```

| Body | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `nom` | `string` | **Required**. Un nom |
| `dateDeRendu` | `string` | **Required**. date du rendu |
| `note` | `string` | **Required**. Une note |
| `subject_id` | `string` | **Required**. id de la matière|
| `teacher_id` | `string` | **Required**. id du professeur l'ayant créé |
| `students_id` | `string` | **Required**. Liste des étudiant l'ayant rendu |

#### Récupérer tout les assignments

```http
  GET /api/assignments
```

#### Mise à jour d'un assignment

```http
  PUT /api/assignments
```

| Body | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `nom` | `string` | **Optionel**. Un nom |
| `dateDeRendu` | `string` | **Optionel**. date du rendu |
| `note` | `string` | **Optionel**. Une note |
| `subject_id` | `string` | **Optionel**. id de la matière|
| `teacher_id` | `string` | **Optionel**. id du professeur l'ayant créé |
| `students_id` | `string` | **Optionel**. Liste des étudiant l'ayant rendu |


#### Récupérer un assignment par sont id

```http
  GET /api/assignments/:id 
```
| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `id` | `string` | **Required**. id de l'assignment à récupérer |

#### Supression d'un assignment par sont id

```http
  DELETE /api/assignments/:id  
```
| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `id` | `string` | **Optionel**. id de l'assignment à supprimer |


### Subject (Matière)

#### Enregistrer un nouveau subject

```http
  POST /api/subjectsubject
```

| Body | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `id` | `string` | **Required**. Une id |
| `title` | `string` | **Required**. Nom de la matière |
| `picture` | `string` | **Required**. Url d'une image |
| `teacher_id` | `string` | **Required**. id du professeur l'ayant créé |

#### Récupérer un subject

```http
  GET /api/subjectsubject
```

| Body | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `id` | `string` | **Required**. Une id |
| `title` | `string` | **Required**. Nom de la matière |
| `picture` | `string` | **Required**. Url d'une image |
| `teacher_id` | `string` | **Required**. id du professeur l'ayant créé |

#### Récupérer tout les subjects

```http
  GET /api/subjects
```

#### Commentaire

#### Enregistrer un commentaire

```http
  POST /api/comment
```

| Body | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `id` | `string` | **Required**. Une id |
| `teacher_id` | `string` | **Required**. id du professeur l'ayant créé |
| `assignment_id` | `string` | **Required**. id de l'assignment|
| `comment` | `string` | **Required**.  Le commentaire|

#### Récupérer les commentaire pour un assignment

```http
  POST /api/comments/:assignmentId
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `assignmentId` | `string` | **Required**. id de l'assignment |
