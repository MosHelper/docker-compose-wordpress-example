# Docker Compose Wordpress
Support Docker Swarm

## How to use
If you do not use Docker Swarm. You should remove 
```
deploy:
      replicas: 1
```
in `docker-compose.yml`

### Config
- In `custom.php.ini` is php config for example
 upload_max_filesize, memory_limit, ...
- In `docker-compose.yml` is config docker container for example
 port, ...

### Start New Project
1. Run Command 

```
docker stack deploy -c docker-compose.yml wordpress1
```
- `wordpress1` is stack name

2. Go to http://localhost:8080 and install Wordpress

### Started with a project already
1. Copy `Your Wordpress` to `www`
2. Edit Database Connect in `wp-config.php`
3. Run Command 

```
docker stack deploy -c docker-compose.yml wordpress1
```

- `wordpress1` is stack name
4. Go to http://localhost:8080 