# Run prometheus and Grafana in Docker-compose

The fastest way to get everything running. 

1. Install Docker
2. Open a terminal in this directory (where this file is)
3. docker-compose up
4. open http://localhost:3000
5. Have fun.


## Run it

Create an IAM user with the correct profile as described in https://github.com/nerdswords/yet-another-cloudwatch-exporter/blob/master/README.md

If you don't already have one, add a profile to your `~/.aws/config` file:

```
[profile my_profile]
sso_region = eu-west-1
```

Add an API key in your `~/.aws/credentials` file with the same name as your profile. Make sure'
you don't leak these credentials, otherwise adverseries can get valuable information about
your system:

```
[my_profile]
aws_access_key_id = XXXXYYYYZZZZ
aws_secret_access_key = xxXXyyYYzzYY1122zzz
```

Create an `.env` file referencing to your config and credentials in youar `~/.aws` folder:

```
AWS_REGION="eu-west-1"
AWS_PROFILE="my_profile"
```

Start your docker compose (this will output logs to the terminal):

```bash
docker-compose up
```

Add `-d` for running it in the background continuously.
Go to http://localhost:3000 to see the cool graphs in grafana. User is `admin`, password is `admin`.
For direct prometheus access , see http://localhost:9090 (but please use grafana)

## Rebuilding:

```bash
docker-compose down
docker-compose up -d --build
```

## Checking logs and process

```bash
docker-compose logs -f
docker-compose ps
```

See https://github.com/nerdswords/yet-another-cloudwatch-exporter

