# Multi-Service Docker Compose with Nginx Reverse Proxy

This project demonstrates a multi-service architecture using Docker Compose with an Nginx reverse proxy.

## Architecture

- **Nginx Reverse Proxy**: Routes requests to appropriate backend services
  - `/service1/*` routes to Service 1 (Go)
  - `/service2/*` routes to Service 2 (Python Flask)
- **Service 1**: Lightweight Go HTTP service
- **Service 2**: Python Flask HTTP service

## Features

- Single entry point via Nginx on port 8080
- Path-based routing
- Request logging with timestamps
- Health checks for all services
- Bridge networking between containers

## Prerequisites

- Docker
- Docker Compose

## Running the Application

To build and start all services:

```bash
docker-compose up --build
```
