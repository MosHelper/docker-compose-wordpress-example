# Docker Compose Wordpress
Support Docker Swarm
## 1. Clone 
```
git clone https://github.com/MosHelper/docker-compose-wordpress-example.git docker-wordpress
```
## 2. File
```
docker-wordpress                <- Project Folder
│--- custom.php.ini             <- php config
│--- docker-compose.yml         <- Do not use Docker Swarm
│--- docker-stack-deploy.yml    <- use Docker Swarm
│--- README.MD
└─── www                        <- Wordpress Folder
    |--- README.MD
```
## 3. How to use

### 3.1 Config
- In `custom.php.ini` is php config for example
 upload_max_filesize, memory_limit, ...
- In `docker-stack-deploy.yml` is config docker container for example
 port, ...

### 3.2 Docker Compose
#### Start New Project
1. Run Command 
```
docker-compose up -d
```
2. Go to http://localhost:8080 and install Wordpress

#### Started with a project already
1. Copy `Your Wordpress` to `www`
2. Edit Database Connect in `wp-config.php`
3. Run Command 
```
docker-compose up -d
```
4. Go to http://localhost:8080 

### 3.3 Docker Swarm
If you do use Docker Swarm. Config Stack 
```
deploy:
      replicas: 1 <- Change 1 to 2, 3, 4, ... as you want.
```
in `docker-stack-deploy.yml`
#### Start New Project
1. Run Command 

```
docker stack deploy -c docker-stack-deploy.yml wordpress1
```
- `wordpress1` is stack name

2. Go to http://localhost:8080 and install Wordpress

#### Started with a project already
1. Copy `Your Wordpress` to `www`
2. Edit Database Connect in `wp-config.php`
3. Run Command 

```
docker stack deploy -c docker-stack-deploy.yml wordpress1
```

- `wordpress1` is stack name
4. Go to http://localhost:8080 