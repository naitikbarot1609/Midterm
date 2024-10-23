This project is a Flask-based web application with continuous integration and deployment (CI/CD) pipelines using GitHub Actions and Jenkins. The application is containerized with Docker and the Docker image is published to Docker Hub.

Structure Of my repository.
  -.github/workflows/ci.yml
  - app.py
  - Dockerfile
  - test_app.py
  - requirement.txt

Prerequisites to run the application -
Python 3.8 or later
Docker
Git

Clone the Repository - 
https://github.com/naitikbarot1609/Midterm.git 

Install dependency - 
pip install -r flask

Running the Flask App Locally - 
export FLASK_APP=app.py
flask run

Running Tests - 
pytest

Steps to build Docker Image ->

1) Build Docker Image - docker build -t flask-app .

2) Run the Docker Container - docker run -p 5000:5000 flask-app

3) Push Docker Image to Docker Hub -
docker login
docker tag flask-app your-dockerhub-username/flask-app:latest
docker push your-dockerhub-username/flask-app:latest

Steps to build CICD Pipeline -

The CI pipeline is defined in .github/workflows/ci.yml and performs:
- Trigger on push and pull on main branch
- Checkout the code
- Set up Python environment
- Install dependencies
- Run tests
- Log in to Docker Hub
- Build Docker image
- Push Docker image to Docker Hub




