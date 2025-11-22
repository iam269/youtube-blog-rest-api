# YouTube Blog REST API 🚀

[![License: ISC](https://img.shields.io/badge/License-ISC-blue.svg)](https://opensource.org/licenses/ISC) ![Node.js](https://img.shields.io/badge/Node.js-43853D?style=flat&logo=node.js&logoColor=white) ![Express.js](https://img.shields.io/badge/Express.js-404D59?style=flat&logo=express&logoColor=white) ![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=flat&logo=mongodb&logoColor=white)

A comprehensive and robust REST API built with Express.js and MongoDB for powering a dynamic YouTube-style blog platform. This API provides full-stack functionality for user management, content creation, categorization, and media uploads, enabling developers to build engaging blogging applications with ease. 📝✨🔥

## 🌟 Key Features

- **🔐 Advanced Authentication System**: Secure user registration and login with bcrypt password hashing and JWT-like session management
- **👤 User Profile Management**: Complete CRUD operations for user accounts with profile updates and secure deletion
- **📚 Dynamic Category System**: Create and manage blog categories for organized content structure
- **📝 Rich Post Management**: Full CRUD operations for blog posts with author verification and content filtering
- **🖼️ Media Upload Capabilities**: Seamless image upload and storage using multer middleware
- **🔍 Flexible Querying**: Advanced post filtering by user, category, and other parameters
- **🗄️ Scalable Database Integration**: MongoDB with Mongoose ODM for efficient data modeling and querying
- **⚡ Optimized Development Workflow**: Nodemon for automatic server restarts during development
- **🔒 Security First**: Input validation, error handling, and secure data practices

## 🛠️ Technology Stack

| Component | Technology | Description |
|-----------|------------|-------------|
| **Runtime** | Node.js | Server-side JavaScript runtime |
| **Framework** | Express.js | Fast, unopinionated web framework |
| **Database** | MongoDB | NoSQL document database |
| **ODM** | Mongoose | Elegant MongoDB object modeling |
| **Authentication** | bcrypt | Password hashing library |
| **File Uploads** | multer | Middleware for handling multipart/form-data |
| **Development** | nodemon | Automatic server restart on file changes |
| **Environment** | dotenv | Environment variable management |

## 📋 Prerequisites

Before running this application, ensure you have the following installed:

- 🟢 **Node.js** (v14 or higher) - [Download here](https://nodejs.org/)
- 🍃 **MongoDB** (v4.0 or higher) - [Download here](https://www.mongodb.com/try/download/community)
- 📦 **npm** or **yarn** package manager

## 🚀 Installation & Setup

1. **Clone the Repository** 📥
   ```bash
   git clone https://github.com/your-username/youtube-blog-rest-api.git
   cd youtube-blog-rest-api
   ```

2. **Install Dependencies** 📦
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Environment Configuration** ⚙️
   Create a `.env` file in the root directory:
   ```env
   MONGO_URL=mongodb://localhost:27017/youtube-blog
   PORT=5000
   ```

4. **Start MongoDB** 🗄️
   Ensure MongoDB is running on your system.

5. **Run the Application** ▶️
   ```bash
   npm start
   ```
   The server will start on `http://localhost:5000` 🚀

## 📁 Project Structure

```
youtube-blog-rest-api/
├── 📂 models/           # Database models
│   ├── Category.js     # Category schema
│   ├── Post.js         # Post schema
│   └── User.js         # User schema
├── 📂 routes/           # API route handlers
│   ├── auth.js         # Authentication routes
│   ├── categories.js   # Category management routes
│   ├── posts.js        # Post CRUD routes
│   └── users.js        # User management routes
├── 📂 images/           # Uploaded media storage
├── index.js            # Main application entry point
├── package.json        # Project dependencies and scripts
├── yarn.lock           # Dependency lock file
└── README.md           # Project documentation
```

## 📡 API Documentation

### Base URL
```
http://localhost:5000/api
```

### Authentication Endpoints 🔐

#### Register User
- **POST** `/auth/register`
- **Description**: Create a new user account
- **Request Body**:
  ```json
  {
    "username": "johndoe",
    "email": "john@example.com",
    "password": "securepassword"
  }
  ```
- **Response**: User object (excluding password)

#### Login User
- **POST** `/auth/login`
- **Description**: Authenticate user credentials
- **Request Body**:
  ```json
  {
    "username": "johndoe",
    "password": "securepassword"
  }
  ```
- **Response**: User object (excluding password)

### User Management 👤

#### Get User
- **GET** `/users/:id`
- **Description**: Retrieve user information by ID

#### Update User
- **PUT** `/users/:id`
- **Description**: Update user profile (users can only update their own accounts)
- **Request Body**: Any user fields to update

#### Delete User
- **DELETE** `/users/:id`
- **Description**: Delete user account and all associated posts

### Post Management 📝

#### Create Post
- **POST** `/posts`
- **Description**: Create a new blog post
- **Request Body**:
  ```json
  {
    "title": "My First Post",
    "desc": "Post description",
    "photo": "image.jpg",
    "username": "johndoe",
    "categories": ["tech", "javascript"]
  }
  ```

#### Get Post
- **GET** `/posts/:id`
- **Description**: Retrieve a specific post by ID

#### Get All Posts
- **GET** `/posts`
- **Query Parameters**:
  - `user`: Filter by username
  - `cat`: Filter by category
- **Description**: Retrieve all posts or filter by user/category

#### Update Post
- **PUT** `/posts/:id`
- **Description**: Update an existing post (authors can only update their own posts)

#### Delete Post
- **DELETE** `/posts/:id`
- **Description**: Delete a post (authors can only delete their own posts)

### Category Management 📚

#### Create Category
- **POST** `/categories`
- **Description**: Create a new category
- **Request Body**:
  ```json
  {
    "name": "Technology"
  }
  ```

#### Get All Categories
- **GET** `/categories`
- **Description**: Retrieve all available categories

### File Upload 🖼️

#### Upload Image
- **POST** `/upload`
- **Description**: Upload an image file
- **Content-Type**: `multipart/form-data`
- **Form Field**: `file`

## 🔧 Environment Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `MONGO_URL` | MongoDB connection string | `mongodb://localhost:27017/youtube-blog` |
| `PORT` | Server port | `5000` |

## 💡 Inspiration

This project was inspired by [Safak's YouTube Blog REST API Tutorial](https://github.com/safak/youtube/tree/blog-rest-api#).

## 🤝 Contributing

Contributions are welcome! 🎉 Please follow these steps:

1. Fork the repository 🍴
2. Create a feature branch: `git checkout -b feature/amazing-feature` 🌿
3. Commit your changes: `git commit -m 'Add amazing feature'` 💾
4. Push to the branch: `git push origin feature/amazing-feature` 📤
5. Open a Pull Request 🚀

## 📄 License

This project is licensed under the ISC License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Safak** - [GitHub Profile](https://github.com/safak)

---

⭐ If you found this project helpful, please give it a star! ⭐

Built with ❤️ using Node.js, Express.js, and MongoDB