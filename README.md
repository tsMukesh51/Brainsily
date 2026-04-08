# Brainsily – Full Stack Application

Brainsily is a backend-driven application for storing and organizing content (notes, links, ideas), built with a strong emphasis on **clean architecture, data validation, and secure APIs**.

🔗 **Live Demo**: https://brainsily.vercel.app/

---

## **Table of Contents**

1. [Project Overview](#project-overview)
2. [Tech Stack](#tech-stack)
3. [Setup Instructions](#setup-instructions)
4. [Features](#features)
5. [Screenshots](#screenshots)
6. [Acknowledgements](#acknowledgements)

---

## Project Overview

Brainsily allows users to manage their personal knowledge in a structured way, supporting creation, retrieval, and organization of content.

This project focuses on:
* Designing scalable **REST APIs**
* Implementing robust **validation with Zod**
* Handling **authentication and authorization**
* Structuring a clean full-stack architecture

---

## Tech Stack

### Frontend
- React 18
- React Router DOM 7
- TypeScript
- TailwindCSS
- Axios
- Vite
- Zod (validation)

### Backend
- Node.js + Express.js
- TypeScript
- MongoDB (Mongoose)
- JWT Authentication
- Zod (validation)
- bcrypt (password hashing)
- dotenv

---

## Architecture


```mermaid
graph TD
    A[Client Request] --> B[Express.js Server]
    B --> C["Middleware<br>(Authentication & Validation)"]
    C --> D["Controllers<br>(API Endpoints)"]
    D --> E["Services<br>(Business Logic)"]
    E --> F["MongoDB<br>(via Mongoose)"]
    F --> G["Models<br>(User, Content, Tag, ContentTagLink)"]
    G --> E
    E --> D
    D --> H[Response to Client]

    %% Styling for better readability
    classDef client fill:#f9f,stroke:#333,stroke-width:2px,color:#100c08;
    classDef server fill:#bbf,stroke:#333,stroke-width:2px,color:#100c08;
    classDef database fill:#bfb,stroke:#333,stroke-width:2px,color:#100c08;
    class A client;
    class B,C,D,E server;
    class F,G database;
```

The Brainsily backend is a MERN-based application built with Express.js, managing API endpoints in `index.ts` with JWT authentication and Mongoose schemas (`db.ts`) for User, Content, Tag, and ContentTagLink models. The `middleware/user.ts` handles authentication, while `Utils` and `types` support encryption and type safety. Data flows from API requests to MongoDB storage, validated by Zod—all custom-built with no external services. It’s a proof-of-concept focused on functionality and growth.

---

## Features

* JWT-based authentication & authorization
* Create and manage notes, links, and content
* Schema validation using **Zod**
* Structured API design with clear separation of concerns
* Responsive frontend with React

---

## Engineering Focus

* Clean API design and separation of concerns
* Strong validation patterns using Zod
* Secure authentication flows
* Full-stack integration with clear boundaries

---

## Limitations / Future Improvements

* Add role-based access control (RBAC)
* Improve search and filtering capabilities
* Add pagination and indexing optimizations
* Introduce caching layer (Redis)
* Add rate limiting for APIs

---

## Setup Instructions

### Prerequisites
- Node.js (v18+)
- npm / yarn
- MongoDB (local or cloud)

---

### 1. Clone Repository
```bash
git clone https://github.com/tsMukesh51/WebDev.git
```

---

### 2. Setup Backend
```bash
cd backend

npm install
```

Create `.env`:
```env
JWT_SECRET=your_secret
MONGO_URL=your_mongodb_url
SHRD_SECRET=your_shared_secret
```

Run backend:
```bash
npm run dev
```

Backend runs on:
```
http://localhost:3000
```

---

### 3. Setup Frontend
```bash
cd ../frontend

npm install
npm run dev
```

Frontend runs on:
```
http://localhost:5173
```

---

## Environment Variables

| Variable    | Description |
|------------|------------|
| JWT_SECRET | JWT signing key |
| MONGO_URL  | MongoDB connection string |
| SHRD_SECRET | Secret for shared links |


Find API Doc in [endpoint.md](./backend/endpoints.md)

---

## Screenshots

1. **Welcome Page**
   ![Welcome Page screenshot](./frontend/screenshots/Welcome.png)

2. **Login Page**
   ![Login Page screenshot](./frontend/screenshots/Authentication.png)

3. **Dashboard Overview**
   ![Dashboard screenshot](./frontend/screenshots/Dashboard.png)

4. **Adding New Content**
   ![Adding New Content screenshot](./frontend/screenshots/CreateTweet.png)

5. **Selecting a Content Type**
   ![Selecting Content Type screenshot](./frontend/screenshots/Catergorize.png)

---

## Acknowledgements

- Thanks to **Kirat** for guidance during development
- Built as part of hands-on full-stack learning

---

<!-- ## **License**
This project currently does not have a license. If you'd like to add one, consider reviewing the [Open Source Initiative](https://opensource.org/licenses) to select a suitable license for your project. -->


