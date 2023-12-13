# pg-dev

A simple, Docker-based Postgres database service for use during development

## User Guide 

### Setup

1. Copy the `.env.example` file to `.env`
2. Update the environment variables in `.env` as desired. To protect any secret values, ensure that the `.env` file will be ignored by any applicable version control.
3. Follow direction in the [Running section](#running) to start your database service.
4. Once you confirm the service is running via CLI output, follow the directions in the [Connecting section](#connecting) to connect to the database and start using it.

### Running

```docker compose up```

### Connecting

From the CLI:

```sh
psql \
  -h localhost \
  -p $HOST_PORT \
  -d $DATABASE_NAME \
  -U $DATABASE_USERNAME \
  --password $DATABASE_PASSWORD
```

For a GUI experience, use [pgAdmin](https://www.pgadmin.org/).

### Backing up your data

By default, your database data will be persisted outside of the container service to the `./.volume` directory on the host. This volume is portable and can be backed up. By replacing this directory with a backup, you can reload the database from prior state.