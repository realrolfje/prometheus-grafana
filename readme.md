# Run prometheus and Grafana in Docker-compose

The fastest way to get everything running. 

1. Install Docker
2. Open a terminal in this directory (where this file is)
3. docker-compose up -d
4. open http://localhost:3000
5. Have fun.


## Run it

```bash
docker-compose up -d
```

Go to http://localhost:3000 to see the cool graphs in grafana. User is `admin`, password is `admin`.

For direct prometheus access , see http://localhost:9090 (but please use grafana)

## Rebuilding:

```bash
docker-compose down
docker-compose up -d --build --force-rebuild
```

## Checking logs and process

```bash
docker-compose logs -f
docker-compose ps
```

