# What's different

This deployment stack uses the golang implementation of sync server instead of the official Ruby server.
This results in significantly smaller image size and better performance.
The golang server uses SQLite database which is a single file, and is much easier to self host for personal use.

# Caution

This stack is still a Work In Progress. We're actively evaluating it.
Please do not use it in production (yet).

# Deployment instruction

```shell
# Start the stack
docker-compose up -d

# All done. Now go to http://127.0.0.1:5000/ and fill in http://127.0.0.1:3000/api to use your own server.
# You can also go to the official web app site at https://app.standardnotes.org/ .
```

