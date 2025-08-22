# Core Banking

A modern, secure, and scalable banking application built with **Django REST Framework** and **PostgreSQL**, featuring **UV** for ultra-fast package management.

![Core-Banking](https://img.shields.io/badge/status-active-success)  
![Python](https://img.shields.io/badge/Python-3.13-blue)  
![Django](https://img.shields.io/badge/Django-4.2-green)  
![Docker](https://img.shields.io/badge/Docker-✓-blue)  

---

## ✨ Features

- **User Authentication & Authorization**
  - JWT-based authentication
  - OTP verification
  - Role-based access control
  - Session management

- **Account Management**
  - Create and manage bank accounts
  - Multiple currency support
  - Transaction history
  - Balance tracking

- **Card Services**
  - Virtual and physical card management
  - Card activation/deactivation
  - Transaction limits

- **Security**
  - Secure password policies
  - Suspicious activity detection
  - Rate limiting
  - CSRF protection

- **Admin Dashboard**
  - User management
  - Transaction monitoring
  - System configuration

---

## 🚀 Tech Stack

- **Backend**: Django 4.2  
- **Database**: PostgreSQL  
- **Cache & Message Broker**: Redis  
- **Task Queue**: Celery  
- **API Documentation**: DRF Spectacular (OpenAPI 3)  
- **Containerization**: Docker  
- **Cloud Storage**: Cloudinary  
- **Package Management**: [UV](https://github.com/astral-sh/uv)  
- **Email Service**: Celery Email  

---

## 🛠️ Prerequisites

- Docker and Docker Compose  
- Python 3.13 (for local development)  
- [UV](https://github.com/astral-sh/uv) (Recommended for faster development)  

---

## 🚀 Quick Start

### Using Docker (Recommended)

```bash
# Clone the repository
git clone https://github.com/yourusername/nextgen-bank.git
cd nextgen-bank

# Copy and configure environment variables
cp .envs/.env.example .envs/.local
# Edit .envs/.local with your configuration

# Build and start containers
make up

# Run database migrations
make migrate

# Create superuser (admin)
make superuser
```

## 🌐 Access the Application

API → http://localhost:8000

Admin → http://localhost:8000/admin

API Docs → http://localhost:8000/api/v1/schema/swagger-ui/


## 🛠 Development
```bash
Package Management with UV

This project uses UV for fast Python package management:

# Install UV (if not installed)
curl -sSf https://astral.sh/uv/install.sh | sh

# Install dependencies
uv pip install -r requirements/local.txt

# Install in development mode
uv pip install -e .

# Update dependencies
uv pip compile requirements/base.in -o requirements/base.txt
uv pip compile requirements/local.in -o requirements/local.txt
```


## ⚙️ Environment Variables
```bash
# Django
DEBUG=True
SECRET_KEY=your-secret-key
DJANGO_SETTINGS_MODULE=config.settings.local

# Database
POSTGRES_DB=banker
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
POSTGRES_HOST=postgres
POSTGRES_PORT=5432

# Redis
REDIS_URL=redis://redis:6379/0

# Celery
CELERY_BROKER_URL=redis://redis:6379/1
CELERY_RESULT_BACKEND=redis://redis:6379/1

# Email
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USE_TLS=True
EMAIL_HOST_USER=your-email@gmail.com
EMAIL_HOST_PASSWORD=your-email-password
DEFAULT_FROM_EMAIL=your-email@gmail.com

# Cloudinary
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
```