# arm-gosu

[![Build](https://github.com/jahrik/arm-gosu/actions/workflows/build.yml/badge.svg)](https://github.com/jahrik/arm-gosu/actions/workflows/build.yml)

Multi-arch Ubuntu base image with [gosu](https://github.com/tianon/gosu) and a step-down entrypoint. Set `GOSU_USER` to drop from root to any uid/gid; set `GOSU_CHOWN` to chown directories first.

## Run

```bash
docker run --rm -e GOSU_USER=nobody:nogroup jahrik/arm-gosu:latest id -un
# nobody
```

## Build

```bash
just build
just push
```

CI: PR builds + step-down check; merge to main pushes multi-arch (amd64/arm64/armv7) to Docker Hub.
