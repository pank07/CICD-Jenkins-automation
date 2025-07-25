- 🧩 All Pipeline Stages Passed — No Errors
<img width="1356" height="731" alt="462932290-4fdfeab5-4cf4-4e9f-b93f-a84b4da754bb" src="https://github.com/user-attachments/assets/e61a7199-acc5-4253-944e-a6eaf0813db6" />
# Installation of jenkins.
- Step:1 Update system
```
  sudo apt update && sudo apt upgrade -y
  ```
- Step:2 Install java (Jenkins needs it)
  ```
  sudo apt install openjdk-17-jdk -y
  ```
  
- Step:3 Confirm installation
  ```
  java -version
  ```
  
- Step:4 Add jenkins package Repository
  ```
  curl -fsSL https://pkg.jenkins.io/debian/jenkins.io.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
```
 
- Step:5 Now add the Repo
```
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
```

- Step:6 Update and install jenkins
```
sudo apt update
sudo apt innstall jenkins -y
```
- Step:7 Start and Enable Jenkins
```
sudo systemctl start jenkins
sudo systemctl enable jenkins
``
- Step:8 Check status
```
sudo systemctl status jenkins
```
- Step:9 Open Port 8080 (UFW or Firewall)
```
sudo ufw allow 8080
sudo ufw reload
```

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
