# Microservices Environment - NestJS with API Gateway

This repository represents the main workspace for a microservices architecture built with [NestJS](https://nestjs.com/). It consolidates multiple microservices into a single environment using Git submodules, enabling centralized management and simplified deployment.

## Overview

The project consists of:

1. **API Gateway**
   The main entry point for all requests, routing messages to the appropriate microservices.
   - **Framework**: NestJS
   - **Transport Layer**: Redis

2. **Microservices**
   - **Auth**: Handles authentication and user management.
   - **Blog**: Manages blog posts, categories, and related data.
   - **Email**: Sends transactional emails and notifications.

This repository uses **Git submodules** to manage individual microservice repositories. The structure is as follows:

## Repository Structure

This repository uses **Git submodules** to manage individual microservice repositories. The structure is as follows:

```plaintext
root/
├── api-gateway/    # API Gateway repository
├── auth/           # Auth microservice repository
├── blog/           # Blog microservice repository
└── email/          # Email microservice repository
```

## Prerequisites

- **Node.js**: Ensure Node.js is installed.
  Download and install it from the official site: Node.js.

- **Redis**: Install (Optional if using Docker Compose. See below) and run a Redis server for the transport layer. [Redis](https://redis.io/kb/doc/1hcec8xg9w/how-can-i-install-redis-on-docker)

- **MongoDb**: Install (Optional if using Docker Compose. See below) and run a MongoDB server for microservice data. [MongoDB](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-community-with-docker/)

- **Docker**: Optionally, you can run everything with Docker. [Docker](https://www.docker.com/)

- **Nest js CLI**: Install Nest js CLI. [NestJS](https://nestjs.com/)

## Repository Content

- **Docker Compose File**: Includes an example `docker-compose.yml` for creating the entire required environment on Docker, including Redis and MongoDB databases.

- **AWS CodeBuild**: Contains a "not production-ready" example of a `buildspec.yml` file for deploying services to AWS Elastic Container Service.

## Installation

### Using Node and Npm

- **Install workspace dependencies**: To install the workspace dependencies, run:

```bash
$ nvm use
$ npm install
```

- **Install microservices dependencies**: To install dependencies for all microservices, use the dedicated command. This will run npm install in all microservice directories

```bash
$ nvm use
$ npm run install-all
```

## Starting the Environment

### Using Node and Npm

To start the entire environment, run:

```bash
$ nvm use
$ npm run start-all
```

### Using Docker

- **Start the environment with docker-compose**: To start the environment with Docker, ensure Docker is installed, then run the following command. This will launch a MongoDB instance, a Redis server, and all services:

```bash
$ docker compose up
```
