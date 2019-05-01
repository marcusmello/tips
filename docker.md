# Cheat Sheet for some Docker commands

## I - docker

### Volume path (on linux)

    /var/lib/docker/volumes/ (only accessible by root user)

## II - docker-compose

### Buid an image of especific service

    docker compose build [options] [--build-arg key=val...] [service_name]

Options:  

    --compress              Compress the build context using gzip.  
    --force-rm              Always remove intermediate containers.  
    --no-cache              Do not use cache when building the image.  
    --pull                  Always attempt to pull a newer version of the image.  
    -m, --memory MEM        Sets memory limit for the build container.  
    --build-arg key=val     Set build-time variables for services.  
    --parallel              Build images in parallel.  

### Run a command inside a container service

    docker-compose exec [service_name] [command]

## References

### Volume

> https://docs.docker.com/storage/#start-a-service-with-volumes

