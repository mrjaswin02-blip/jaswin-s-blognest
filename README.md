#  AI BlogNest

**AI BlogNest** is a full-stack AI-powered blogging platform that allows users to create, manage, discover, and interact with blog content. The application combines a modern web interface with a Node.js/Express.js backend, MongoDB database, JWT authentication, and Google Gemini AI integration.

---

##  Project Overview

AI BlogNest provides a centralized platform for creating and managing blog posts with the assistance of Artificial Intelligence.

The application supports user authentication, blog management, categories, tags, comments, administrative controls, and AI-powered content generation.

The project is designed with a separate frontend and backend architecture:

```text
Browser
   │
   ▼
Client (HTML + CSS + JavaScript)
   │
   ▼
Node.js + Express.js REST API
   │
   ├───────────────► MongoDB Atlas
   │
   └───────────────► Google Gemini AI
```

---

## ✨ Features

### 👤 User Authentication

* User registration
* User login
* JWT-based authentication
* Secure authenticated API requests
* User profile management
* Role-based access control
* Logout functionality

### 📝 Blog Management

* Create blog posts
* Edit existing blogs
* Delete blogs
* View published blogs
* Manage personal blogs
* Blog status management
* Blog categories
* Blog tags

### 🤖 AI Features

* AI-assisted blog content generation
* Google Gemini AI integration
* AI-powered content assistance
* Gemini embedding support for semantic-search-related functionality

### 💬 Comments

* Add comments to blog posts
* Manage comments through authenticated APIs
* Comment-related database management

### 👨‍💼 Admin Features

* Administrative dashboard
* User management
* Blog moderation
* Pending/published post management
* Category management
* Administrative role protection

### 🔎 Content Discovery

* Blog listing
* Category-based content
* Tag-based content
* Search/content discovery functionality
* Individual blog pages

### 🗄️ Database

* MongoDB Atlas integration
* Mongoose ODM
* Persistent storage for users, posts, categories, tags, and comments

---

## 🛠️ Technology Stack

### Frontend

* HTML5
* CSS3
* Modern JavaScript (ES6+)
* Fetch API
* DOM manipulation
* Browser APIs

### Backend

* Node.js
* Express.js
* REST API
* Mongoose

### Database

* MongoDB
* MongoDB Atlas

### Artificial Intelligence

* Google Gemini AI
* Gemini generation model
* Gemini embedding model

### Authentication & Security

* JSON Web Tokens (JWT)
* bcrypt.js
* Role-based authorization
* Environment variables for sensitive configuration

### Development Tools

* Visual Studio Code
* Postman / Thunder Client
* npm
* Git & GitHub

---

## 📂 Project Structure

```text
AI-BlogNest/
│
├── Client/
│   ├── index.html
│   ├── login.html
│   ├── register.html
│   ├── dashboard.html
│   ├── create-blog.html
│   ├── edit-blog.html
│   ├── blog.html
│   ├── my-blogs.html
│   ├── profile.html
│   ├── admin.html
│   │
│   ├── css/
│   │   └── style.css
│   │
│   ├── js/
│   │   ├── api.js
│   │   ├── auth.js
│   │   ├── home.js
│   │   ├── blog.js
│   │   ├── dashboard.js
│   │   ├── create-blog.js
│   │   ├── edit-blog.js
│   │   ├── profile.js
│   │   └── admin.js
│   │
│   └── images/
│
├── Server/
│   ├── app.js
│   ├── server.js
│   │
│   ├── config/
│   │   ├── db.js
│   │   └── env.js
│   │
│   ├── controllers/
│   │   ├── aiController.js
│   │   ├── authController.js
│   │   ├── categoryController.js
│   │   ├── commentController.js
│   │   ├── postController.js
│   │   └── tagController.js
│   │
│   ├── middleware/
│   │   ├── authMiddleware.js
│   │   ├── errorMiddleware.js
│   │   └── roleMiddleware.js
│   │
│   ├── models/
│   │   ├── categoryModel.js
│   │   ├── commentModel.js
│   │   ├── localStore.js
│   │   ├── postModel.js
│   │   ├── tagModel.js
│   │   └── userModel.js
│   │
│   ├── routes/
│   │   ├── aiRoutes.js
│   │   ├── authRoutes.js
│   │   ├── categoryRoutes.js
│   │   ├── commentRoutes.js
│   │   ├── postRoutes.js
│   │   └── tagRoutes.js
│   │
│   └── services/
│       └── geminiService.js
│
├── package.json
├── package-lock.json
├── .env.example
├── .gitignore
└── README.md
```

---

## ⚙️ Requirements

Before running the project, install:

* Node.js
* npm
* MongoDB Atlas account
* Google Gemini API key
* Git

You can verify Node.js and npm installation using:

```bash
node --version
npm --version
```

---

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/AI-BlogNest.git
```

Move into the project directory:

```bash
cd AI-BlogNest
```

### 2. Install Dependencies

```bash
npm install
```

> `node_modules` is intentionally not included in the GitHub repository. Running `npm install` creates it automatically from `package.json` and `package-lock.json`.

---

## 🔐 Environment Configuration

Create a `.env` file in the location expected by the project's environment configuration.

Example:

```env
PORT=3000

MONGODB_URI=your_mongodb_connection_string

GEMINI_API_KEY=your_gemini_api_key

JWT_SECRET=your_jwt_secret

GEMINI_GENERATION_MODEL=gemini-3.6-flash

GEMINI_EMBEDDING_MODEL=gemini-embedding-001
```

### ⚠️ Security Warning

Never commit the real `.env` file to GitHub.

Do not expose:

* MongoDB username
* MongoDB password
* MongoDB connection URI containing credentials
* Gemini API key
* JWT secret

Use `.env.example` to document required variables without exposing their actual values.

---

## 🗄️ MongoDB Configuration

AI BlogNest uses MongoDB for persistent application data.

### Setup

1. Create a MongoDB Atlas cluster.
2. Create a database user.
3. Configure the required network access.
4. Copy the MongoDB connection string.
5. Add it to the `.env` file as:

```env
MONGODB_URI=your_mongodb_connection_string
```

The application connects to MongoDB through Mongoose.

---

## 🤖 Gemini AI Configuration

AI BlogNest integrates Google Gemini for AI-powered functionality.

Configure the Gemini API key in your environment:

```env
GEMINI_API_KEY=your_gemini_api_key
```

Generation model:

```env
GEMINI_GENERATION_MODEL=gemini-3.6-flash
```

Embedding model:

```env
GEMINI_EMBEDDING_MODEL=gemini-embedding-001
```

> Never place the Gemini API key inside frontend JavaScript files.

---

## ▶️ Running the Application

Start the development server using:

```bash
npm run dev
```

The application runs on the configured port.

For the default configuration:

```text
http://localhost:3000
```

The Express server serves the frontend and provides the REST API.

---

## 🔌 API

The backend exposes REST API endpoints for the application's main features.

Example API base URL:

```text
http://localhost:3000/api
```

Example resources include:

```text
/api/auth
/api/posts
/api/categories
/api/comments
/api/tags
/api/ai
```

The exact endpoints and request methods are implemented in the corresponding route files inside:

```text
Server/routes/
```

---

## 🔑 Authentication Flow

AI BlogNest uses JWT-based authentication.

General authentication flow:

```text
User
 │
 ├── Register
 │
 └── Login
       │
       ▼
   Express API
       │
       ▼
   Authentication
       │
       ▼
     JWT
       │
       ▼
Authenticated Requests
```

Protected routes verify the authentication token through the authentication middleware.

Role-based permissions are handled through the role middleware.

---

## 🧠 AI Architecture

AI-related requests are handled through the backend rather than exposing the Gemini API key to the browser.

```text
Client
  │
  ▼
AI REST Endpoint
  │
  ▼
AI Controller
  │
  ▼
Gemini Service
  │
  ▼
Google Gemini API
  │
  ▼
AI Response
  │
  ▼
Client
```

This architecture keeps the Gemini credentials on the server side.

---

## 🛡️ Security

The project follows several security practices:

* JWT authentication
* Password hashing with bcrypt.js
* Role-based authorization
* Environment variables for secrets
* Server-side AI API access
* MongoDB authentication
* Protected backend routes
* Sensitive configuration excluded from Git

### Never commit:

```text
.env
node_modules/
MongoDB credentials
Gemini API keys
JWT secrets
Private credentials
```

---

## 📦 GitHub Repository

The repository should contain the application source code and documentation.

Recommended files:

```text
✅ Client/
✅ Server/
✅ package.json
✅ package-lock.json
✅ .gitignore
✅ .env.example
✅ README.md
```

Do not upload:

```text
❌ node_modules/
❌ .env
❌ Server/data/local_db.json
❌ API keys
❌ Database passwords
❌ JWT secrets
```

---

## 🌐 Deployment

For a complete deployment, AI BlogNest requires both:

1. Frontend
2. Node.js/Express backend

The backend also requires access to:

* MongoDB Atlas
* Gemini API

### Important

GitHub Pages can host static HTML/CSS/JavaScript, but it cannot execute the Node.js/Express backend.

Therefore, a complete AI BlogNest deployment should use a platform that supports Node.js/Express for the backend.

Deployment environment variables should be configured on the hosting platform instead of uploading `.env` to GitHub.

Example production configuration:

```text
GitHub Repository
        │
        ▼
Node.js Hosting
        │
        ├── Express API
        │
        ├── MongoDB Atlas
        │
        └── Gemini AI
        │
        ▼
   Live Application
```

---

## 🧪 Testing

The REST APIs can be tested using:

* Postman
* Thunder Client

Test areas include:

* Authentication
* User management
* Blog creation
* Blog updates
* Blog deletion
* Categories
* Tags
* Comments
* AI endpoints
* Authorization
* Admin operations

---

## 🧰 Development

Recommended development workflow:

```text
1. Clone repository
2. Install dependencies
3. Configure .env
4. Configure MongoDB Atlas
5. Configure Gemini API
6. Start development server
7. Test APIs
8. Test frontend
9. Commit changes
10. Push to GitHub
```

---

## 📝 Environment File Example

Create `.env.example` for other developers:

```env
PORT=3000

MONGODB_URI=

GEMINI_API_KEY=

JWT_SECRET=

GEMINI_GENERATION_MODEL=gemini-3.6-flash

GEMINI_EMBEDDING_MODEL=gemini-embedding-001
```

Do not place real credentials in this file.

---

## 📄 License

This project is developed as an academic/project application.

If you intend to distribute the project publicly, add an appropriate open-source license such as the MIT License.

---

## 👨‍💻 Author

**M. R. Jaswin**

AI BlogNest — AI-Powered Blogging Platform

---

## ⭐ Project Highlights

AI BlogNest combines:

```text
Modern Web Development
        +
REST API Architecture
        +
JWT Authentication
        +
MongoDB
        +
Google Gemini AI
        +
Blog Management
        +
Role-Based Access
        +
AI-Assisted Content
```

The project demonstrates how Artificial Intelligence can be integrated into a full-stack web application to improve the blogging and content-management experience.
