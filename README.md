# image-and-video-gallery-backend-using-mongo-db-and-aws-s3-bucket

This repository contains the backend implementation of a scalable and secure Image & Video Gallery Application. The backend is built using Node.js, Express, MongoDB, and AWS S3 to provide robust functionalities for uploading, retrieving, updating, and deleting media files.

Features
1.User Authentication: Secure login and registration using JWT (JSON Web Tokens).
2.File Upload: Users can upload images and videos to AWS S3, with metadata stored in MongoDB.
3.File Retrieval: Efficient retrieval of media files along with their metadata via API calls.
4.File Update: Seamlessly update/replace existing files without changing their fileId.
5.File Deletion: Remove files from both AWS S3 and MongoDB using fileId.
6.Security: Passwords hashed using bcrypt.js, with secure access to routes using JWT.
7.Scalable Media Storage: AWS S3 integration for high availability and redundancy.

Technologies Used (backend)
1.Node.js & Express: RESTful API development.
2.MongoDB & Mongoose: Storing user data and file metadata.
3.AWS S3: Media file storage and retrieval.
4.JWT: Authentication and route protection.
5.Multer: Handling file uploads to the server.
6.bcrypt.js: Secure password hashing.

# Project Structure
image-video-gallery/
│
├── backend/
│   ├── config/
│   │   └── awsConfig.js       # AWS S3 configuration
│   ├── middlewares/
│   │   ├── authMiddleware.js  # JWT authentication middleware
│   │   └── errorMiddleware.js # Centralized error handling
│   ├── models/
│   │   ├── Image.js           # Image schema
│   │   ├── Video.js           # Video schema
│   │   └── User.js            # User schema
│   ├── routes/
│   │   ├── gallery.js         # File management routes (upload, delete, update, fetch)
│   │   └── auth.js            # User authentication routes
│   ├── app.js                 # Express app entry point
│   └── package.json           # Backend dependencies
│
├── .env                       # Environment variables
├── .gitignore                 # Files to ignore in GitHub

# Environment Variables
Create a .env file in the root directory and include the following:
MONGO_URI=mongodb://localhost:27017/imageVideoGallery
JWT_SECRET=your_jwt_secret
AWS_ACCESS_KEY_ID=your_aws_access_key_id
AWS_SECRET_ACCESS_KEY=your_aws_secret_access_key
AWS_BUCKET_NAME=your_bucket_name
AWS_REGION=your_region

# Installation & Setup
1.Clone the repository:
  git clone https://github.com/your-username/image-video-gallery-backend.git
2.Navigate to backend directory:
  cd image-video-gallery/backend
3.Install dependencies:
  npm install
4.Start the server:
  node app.js
5.server is running now on port 5000
  http://localhost:5000

# API Endpoints
User Authentication
POST /api/auth/register - Register a new user.
POST /api/auth/login - Login and receive JWT.
File Management
POST /api/gallery/upload - Upload a new image or video.
GET /api/gallery/files - Retrieve all uploaded files.
PUT /api/gallery/update/:fileId - Update an existing file.
DELETE /api/gallery/delete/:fileId - Delete a specific file.

Future Enhancements
Implement pagination and sorting for file listings.
Add search functionality.
Improve error handling and validation.
Add unit and integration tests.
Deploy the backend to a cloud service (AWS EC2, DigitalOcean, etc.).

  
