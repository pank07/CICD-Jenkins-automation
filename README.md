
<img width="1356" height="731" alt="462932290-4fdfeab5-4cf4-4e9f-b93f-a84b4da754bb" src="https://github.com/user-attachments/assets/e61a7199-acc5-4253-944e-a6eaf0813db6" />

# Simple Notes App for learning
This is a simple notes app built with React and Django.

## Requirements
1. Python 3.9
2. Node.js
3. React

## Installation
1. Clone the repository
```
git clone https://github.com/pank07/django-notes-app.git
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
