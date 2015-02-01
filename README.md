# Docker configs for development (NginX)
Some Dockerfile configs to create new development area's automatically.

# Basic setup
To use a simple Dockerfile for installation, you need an empty Ubuntu (Virtual) machine. On that Ubuntu instance you need
to (install Docker)[https://docs.docker.com/installation/ubuntulinux/] and make sure you have the latest updates installed.

Update command in Ubuntu:
```php
sudo apt-get update
```

# List of handy Docker commands
Command | Description
------- | -----------
docker images | List all images available to start a new Docker container
docker ps 	  | List all your active Docker containers
docker ps -a  | List all active and inactive Docker containers
docker run [image_url] | Run a new Docker container from an existing image
docker run -ti [image_url] | Run an new Docker container and start an SSH terminal
docker run -d -p 80:80 [image_url] | Run a new Docker container and port forward (e.g. Port 80) to the current host
docker commit [instance_id] [image_url] | Commit a running Docker container to an image
docker push [image_url][:tag] | Push an image to the registry (use a colon to add a tag)
docker exec [instance_id] ps -aux | View the current processes in a running Docker container
docker rm -f [instance_id] | Remove a Docker container to clean up
docker search [image_url] | Search for an image in the Docker registry
docker inspect [instance_id] (Optional | jq .) | Inspect a Docker container and aggregate information (JSON)

# Crate new Docker container from Dockerfile
Command | Description
------- | -----------
docker build -t [image_url] . | Build a new Docker instance from image and the Dockerfile (dot means in current directory)
docker run -Pd  [image_url] | Run a recently created Docker instance and port forward the ports automatically