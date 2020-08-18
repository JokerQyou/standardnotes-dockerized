# standardnotes-dockerized

Self-host your own Standard Notes instance.

# Notice

API server is replaced with [the Golang version][go_server].

# To build

To build [the golang sync server][go_server]:

```shell
docker build -f Dockerfile_go_server -t mcores/standardfile-go .
```

To build [the web app][web_app]:

```shell
docker build -f Dockerfile_web -t mcores/standardnote-web .
```

# To deploy

TBD

[go_server]: https://github.com/tectiv3/standardfile
[web_app]: https://github.com/standardnotes/web

