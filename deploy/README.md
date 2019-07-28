# What's different

This deployment stack uses MariaDB which is compatible with MySQL 5.7 auth plugin, so you don't have to pin to the legacy version of MySQL.

# Caution

This stack is still a Work In Progress. We're actively evaluating it.
Please do not use it in production (yet).

# Deployment instruction

```shell
# Edit .env accordingly (ref to official guide here: https://docs.standardnotes.org/self-hosting/self-hosting-with-docker)

# Start the stack
docker-compose up -d

# Once the database is ready, run a one-time database init task:
docker-compose exec app bundle exec rake db:create db:migrate

# All done. Now go to https://app.standardnotes.org/ and fill in http://127.0.0.1:3000 to use your own server
```

