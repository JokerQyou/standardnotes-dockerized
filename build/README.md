# What's different

This Dockerfile uses multi-stage mechanism to separate build-time and runtime artifacts.
So the resulting image size is significantly smaller than images produced with the official Dockerfile.
It also link the production log to stdout of the running container, so it can be easily viewed / collected / rotated.

# Build instruction

To build the sync server:

```shell
cp Dockerfile_server ruby-server/
cd ruby-server
docker build -t mcores/standardnote-app .
```

To build the web app:

```shell
docker build -t mcores/standardnote-web .
```

