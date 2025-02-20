# Inception

## Project Overview

Inception is a system administration project designed to deepen your knowledge of Docker and containerization. The objective is to set up a small infrastructure composed of various services running in separate Docker containers, orchestrated with `docker-compose` within a Virtual Machine.

## Key Objectives:
- Create Docker images for specific purposes within a personal virtual environment.
- Gain hands-on experience with containerization, deployment, and orchestration using Docker.

## Features
- **NGINX with TLSv1.2 or TLSv1.3**
- **WordPress with PHP-FPM**
- **MariaDB Database**
- **Docker volumes for database and website files**
- **Docker network for container communication**
- **Automatic container restart on failure**
- **Domain name setup (`login.42.fr`) pointing to local IP**
- **Environment variables stored securely in a `.env` file**

## Bonus Features
- **Redis cache for WordPress**
- **FTP server for file management**
- **Static website (non-PHP)**
- **Adminer for database management**
- **Portainer for docker management**

## Installation & Usage
1. Clone the repository:
   ```sh
   git clone https://github.com/Elmehdibennix/Inception_42.git
   cd Inception_42
   ```
2. Configure environment variables in `srcs/.env`
3. Run the project using Makefile:
   ```sh
   make
   ```
4. To stop the project:
   ```sh
   make down
   ```

## Notes
- All Docker images are built manually (no pre-built images allowed except Alpine/Debian base images).
- The `latest` tag is prohibited.
- Credentials must be stored securely in `.env` and ignored by Git.

Happy Dockerizing!
