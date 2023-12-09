# Shorty DB

A database project acting as a backend for shorty

## Running

```docker-compose up```

## Connecting

```sh
psql \
  -h localhost \
  -p $HOST_PORT \
  -d $DATABASE_NAME \
  -U $DATABASE_USERNAME \
  --password $DATABASE_PASSWORD
```

## Backing up your data

After running Shorty DB, stop the container and back up a copy of your local `/data` folder. This volume is mounted to Shorty DB when spinning up a new container instance.