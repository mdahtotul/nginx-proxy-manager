# Quick Setup
#### 1. Install Docker and Docker-Compose

#### 2. Create a docker-compose.yml file similar to this:
```
services:
  app:
    image: 'jc21/nginx-proxy-manager:latest'
    restart: unless-stopped
    ports:
      - '80:80'
      - '81:81'
      - '443:443'
    volumes:
      - ./data:/data
      - ./letsencrypt:/etc/letsencrypt
```
#### 3. Bring up your stack by running
```
docker-compose up -d

# If using docker-compose-plugin
docker compose up -d
```
#### 4. Log in to the Admin UI
When your docker container is running, connect to it on port 81 for the admin interface. Sometimes this can take a little bit because of the entropy of keys.

http://127.0.0.1:81

Default Admin User:
```
Email:    admin@example.com
Password: changeme
```
