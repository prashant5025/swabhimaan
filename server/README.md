# swabhimaan_SIH_2023


## Platfrom Architechture

### Swabhimann is a platform where a POW's person can get a job according to his/her skills and can also get a job according to his/her location. This platform is also useful for the employer to find the right person for the job. This platform is also useful for the NGO's to find the right person for the job. Platform will provide automation services like active notification about jobs and also provide right resouces and material.

## Tech Stack

1. React
2. Node
3. Express
4. MongoDB
5. Socket.io
6. Firebase
7. WebRTC
8. Web Speech API
9. Tailwind CSS

## Public Routes

- Home page 
- About page
- Contact page
- Login page
- Register page

## Auth Routes
- User profile page
- User dashboard page
- User Resourses page
- User Resume page
- Group chat page
- Video call page
- Job page govt | private

# Admin Routes
- Admin dashboard page
- User management page
- Job management page
- Resourses management page


## API Structure

### Routing Structure

| API Route |Http Method  | Description |
|--|--|--|
| /api/users | GET | Get all users |
|  | POST | create a new user |
|  | PUT | update a  users |
|  | DELETE | delete users |
| /api/users/:id | GET | Get a single user |
| /api/jobs | GET | Get all jobs |
| /api/:id/chat | GET | Get all chats |
| /api/:id/join/:id | GET | Join a chat |

### Models Structure

#### User Model

```javascript
{
    name: {
        type: String,
        required: true
    },
    email: {
        type: String,
        required: true,
        unique: true,
        trim: true
    },
    password: {
        type: String,
        required: true
    },
    role: {
        type: String,
        enum: ['user', 'admin'],
        default: 'user'
    },
    profilePic: {
        type: String,
        default: 'https://res.cloudinary.com/djnv06fje/image/upload/v1623928853/avatars/avatar-1_fsuqxx.png'
    },
    resume: {
        type: String,
        default: ''
    },
    bio: {
        type: String,
        default: ''
    },
    status: {
        type: String,
        default: 'Pending'
    },
    googleId: {
        type: String,
        default: ''
    },
    facebookId: {
        type: String,
        default: ''
    },
    createdAt: {
        type: Date,
        default: Date.now
    }
}
```

## API Respone 

> /users/

#### 'GET 200 OK' 
```json
"data": [
    {
    "_id": "6522b3bc202f716e8b090184",
    "name": "test1",
    "email": "test1@gmail.com",
    "password": "$2b$10$.leYCnlj6lWSsXH5pexRg.SWQ84XVQJRV/9lI8tnVjgLkOwcGtxC.",
    "profileCover": "default-cover.jpg",
    "profilePicture": "default-avatar.jpg",
    "role": "user",
    "token": "",
    "createdAt": "2023-10-08T13:50:52.096Z",
    "update": "2023-10-08T13:50:52.000Z",
    "updatedAt": "2023-10-08T13:50:52.096Z",
    "__v": 0
    },
    {
    "_id": "6523a4274efb9ee78b978321",
    "name": "test2",
    "email": "test2@gmail.com",
    "password": "$2b$10$sHnivyb2hLNhroakJyAId.10RydgA/bubPhzKbjDT/ZLKQHWNyi/O",
    "profileCover": "default-cover.jpg",
    "profilePicture": "default-avatar.jpg",
    "role": "user",
    "token": "",
    "createdAt": "2023-10-09T06:56:39.092Z",
    "update": "2023-10-09T06:56:39.000Z",
    "updatedAt": "2023-10-09T06:56:39.092Z",
    "__v": 0
    }
]
```

> /users/auth/register

#### 'POST 200 OK' 

```json
{
  "username": "newuser",
  "email": "newuser@example.com",
  "password": "password",
  "role": "user"
}
``` 

**Response**

-   `201 Created` on success

```json
{
  "id": "789",
  "username": "newuser",
  "email": "newuser@example.com",
  "password": "alsdfuao@#2#$@2liufldsnasdfnkadslkjf",
  "role": "user"
}
```
