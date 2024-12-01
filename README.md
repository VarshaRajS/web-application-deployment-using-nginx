![image](https://github.com/user-attachments/assets/6e7f50b2-8a26-4a5d-9933-f17f53ff82e6)

1. Dockerized my Django application, Nginx, and MySQL database.
2. Configured Nginx as a reverse proxy to handle load balancing and routing requests.
3. Set up a shared network for efficient communication between containers.
4. Leveraged volumes to ensure persistent data storage for MySQL.
5. Automated the deployment process with Jenkins, creating a seamless CI/CD pipeline.

# Simple Notes App 
This is a simple notes app built with React and Django.

## Requirements
1. Python 3.9
2. Node.js
3. React

## Installation
1. Clone the repository
```
git clone  https://github.com/VarshaRajS/web-application-hosting-using-nginx.git
```

2. Build the app
```
docker build -t notes-app .
```

3. Run the app
```
docker run -d -p 8000:8000 notes-app:latest
```

## Nginx

Install Nginx reverse proxy to make this application available

`sudo apt-get update`
`sudo apt install nginx`

