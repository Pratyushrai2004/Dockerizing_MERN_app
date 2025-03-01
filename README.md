Dockerizing React App 🐳⚛️
Overview
This project demonstrates how to containerize a React application using Docker and Docker Compose. It provides an isolated environment, making it easy to deploy and scale the app without worrying about dependencies.

Features 🚀
Containerized React app using Docker
Supports hot-reloading for development
Uses Docker Compose for easy multi-container management
Works across different environments (local, staging, production)
Prerequisites ✅
Ensure you have the following installed before proceeding:

Docker
Docker Compose
Node.js (Optional, for local testing)
Project Structure 📁
bash
Copy
Edit
/dockerizing-react-app  
│── /src                # React source code  
│── /public             # Static assets  
│── /nginx              # Nginx configuration  
│── .dockerignore       # Files to ignore during build  
│── Dockerfile          # Docker configuration for the app  
│── docker-compose.yaml # Defines multi-container setup  
│── package.json        # Dependencies and scripts  
│── README.md           # Documentation  
Installation & Setup ⚙️
1️⃣ Clone the Repository

2️⃣ Build and Run with Docker
Option 1: Using Docker CLI
sh
Copy
Edit
docker build -t my-react-app .
docker run -d -p 3000:3000 --name react_container my-react-app
This will run the React app on http://localhost:3000

Option 2: Using Docker Compose
If using docker-compose.yaml, simply run:

sh
Copy
Edit
docker-compose up --build
Stopping & Restarting the Container 🔄
Stop the running container
sh
Copy
Edit
docker stop react_container
Restart the container
sh
Copy
Edit
docker restart react_container
Remove the container & rebuild
sh
Copy
Edit
docker rm -f react_container
docker-compose up --build
Environment Variables 🌍
Modify the .env file or pass them as arguments:

sh
Copy
Edit
REACT_APP_API_URL=http://localhost:5000
Accessing the App 🌐
After running the container, visit:
👉 http://localhost:3000

If using Nginx for production, visit:
👉 http://localhost:8080

Common Issues & Fixes ❌🔧
Issue	Solution
Cannot connect to Docker daemon	Ensure Docker is running: sudo systemctl start docker
Port already in use	Change the port in docker-compose.yaml
Module not found: axios	Run npm install axios before building
