# Deployment Guide

## Local Deployment

### Using Docker Compose
```bash
docker-compose up --build -d
```

### Check running containers
```bash
docker ps
```

### View logs
```bash
docker-compose logs -f
```

## Production Deployment

### Environment Variables
Make sure all environment variables are set:
```bash
cp .env.example .env
# Fill in production values
```

### Build and Deploy
```bash
docker build -t app:latest .
docker run -d -p 8000:8000 app:latest
```

## CI/CD Pipeline
This project uses GitHub Actions for CI/CD.
Every push to main branch triggers:
1. Automated tests
2. Docker image build
3. Deployment

## Health Check
```bash
curl http://localhost:8000/health
```
