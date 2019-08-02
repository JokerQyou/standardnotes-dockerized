# What's different

This Dockerfile uses multi-stage mechanism to separate build-time and runtime artifacts.
So the resulting image size is significantly smaller than images produced with the official Dockerfile.
It also link the production log to stdout of the running container, so it can be easily viewed / collected / rotated.

# Build instruction

To build [the official sync server][ruby_server] (written in Ruby):

```shell
cp Dockerfile_ruby_server ruby-server/Dockerfile
cd ruby-server
docker build -t mcores/standardnote-app .
```

To build [the golang sync server][go_server]:

```shell
cp Dockerfile_go_server Dockerfile
docker build -t mcores/standardnote-go .
```

To build [the web app][web_app]:

```shell
cp Dockerfile_web Dockerfile
docker build -t mcores/standardnote-web .
```


[ruby_server]: https://github.com/standardfile/ruby-server
[go_server]: https://github.com/tectiv3/standardfile
[web_app]: https://github.com/standardnotes/web

