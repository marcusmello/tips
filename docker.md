# Cheat Sheet for some Docker commands

## I - docker

### Volume path (on linux)

    /var/lib/docker/volumes/ (only accessible by root user)

## II - docker-compose

### .yml file syntax

#### Network Aliases

Aliases (alternative hostnames) for this service on the network. Other containers on the same network can use either the service name or this alias to connect to one of the service’s containers.

Since aliases is network-scoped, the same service can have different aliases on different networks.

    Note: A network-wide alias can be shared by multiple containers, and even by multiple services. If it is, then exactly which container the name resolves to is not guaranteed.

The general format is shown here:

    services:
      some-service:
        networks:
          some-network:
            aliases:
             - alias1
             - alias3
          other-network:
            aliases:
             - alias2

#### Ports Bind

    ports:
      - 'host:container'

### General usage

    docker-compose [-f <arg>...] [options] [COMMAND] [ARGS...]
    docker-compose -h|--help

Options:

    -f, --file FILE             Specify an alternate compose file (default: docker-compose.yml)  
    -p, --project-name NAME     Specify an alternate project name (default: directory name)  
    --verbose                   Show more output  
    --log-level LEVEL           Set log level (DEBUG, INFO, WARNING, ERROR, CRITICAL)  
    --no-ansi                   Do not print ANSI control characters  
    -v, --version               Print version and exit  
    -H, --host HOST             Daemon socket to connect to  
    --tls                       Use TLS; implied by --tlsverify  
    --tlscacert CA_PATH         Trust certs signed only by this CA  
    --tlscert CLIENT_CERT_PATH  Path to TLS certificate file  
    --tlskey TLS_KEY_PATH       Path to TLS key file  
    --tlsverify                 Use TLS and verify the remote  
    --skip-hostname-check       Don't check the daemon's hostname against the name specified in the client certificate  
    --project-directory PATH    Specify an alternate working directory (default: the path of the Compose file)  
    --compatibility             If set, Compose will attempt to convert keys in v3 files to their non-Swarm equivalent  

Commands:  

    build              Build or rebuild services  
    bundle             Generate a Docker bundle from the Compose file  
    config             Validate and view the Compose file  
    create             Create services  
    down               Stop and remove containers, networks, images, and volumes  
    events             Receive real time events from containers  
    exec               Execute a command in a running container  
    help               Get help on a command  
    images             List images  
    kill               Kill containers  
    logs               View output from containers  
    pause              Pause services  
    port               Print the public port for a port binding  
    ps                 List containers  
    pull               Pull service images  
    push               Push service images  
    restart            Restart services  
    rm                 Remove stopped containers  
    run                Run a one-off command  
    scale              Set number of containers for a service  
    start              Start services  
    stop               Stop services  
    top                Display the running processes  
    unpause            Unpause services  
    up                 Create and start containers  
    version            Show the Docker-Compose version information  

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

> <https://docs.docker.com/storage/#start-a-service-with-volumes>
