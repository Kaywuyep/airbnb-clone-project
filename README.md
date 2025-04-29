# Airbnb Clone Project

## Overview

The **Airbnb Clone Project** is a comprehensive, real-world application designed to simulate the development of a robust booking platform similar to Airbnb. This project serves as a capstone experience for learners aiming to sharpen their full-stack development skills, with an emphasis on backend systems, database architecture, API design, and security best practices.

Through this project, learners will gain practical experience building scalable web applications, working with development lifecycles, and collaborating within teams using modern DevOps tools and methodologies.

## Project Goals

- Understand and implement full-stack web development using modern tools and frameworks.
- Build a scalable and secure backend infrastructure.
- Design and optimize relational databases for real-world use cases.
- Develop RESTful APIs to support frontend functionality.
- Practice software engineering principles such as CI/CD, containerization, and security.
- Simulate professional workflows including version control, testing, and deployment pipelines.

## Tech Stack

- **Backend Framework**: Django
- **Database**: MySQL
- **Containerization**: Docker
- **CI/CD**: GitHub Actions
- **Version Control**: Git & GitHub
- **API Design**: RESTful APIs with Django REST Framework (optional enhancement)
- **Other Tools**: Postman (API testing), VSCode (code editor)

## Requirements

To successfully complete the project tasks, learners must:

- Have a [GitHub](https://github.com/Kaywuyep/airbnb-clone-project.git) account to create and manage repositories.
- Be familiar with Markdown syntax for creating and editing `README.md` files.
- Possess prior experience with backend frameworks like **Django** and database systems such as **MySQL**.
- Understand the software development lifecycle practices, including:
  - Application security
  - Continuous Integration/Deployment (CI/CD)
  - Database design and migrations
- Be comfortable using modern tools such as:
  - **Docker**
  - **GitHub Actions** or similar CI/CD platforms

## Getting Started

1. Clone this repository.
2. Set up your virtual environment and install dependencies.
3. Configure your local `.env` file with the necessary environment variables.
4. Run initial migrations and start the development server.

```bash
git clone https://github.com/Kaywuyep/airbnb-clone-project.git
cd airbnb-clone
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
