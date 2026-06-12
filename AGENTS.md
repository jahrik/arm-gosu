# AGENTS.md

Multi-arch base image: Ubuntu + [gosu](https://github.com/tianon/gosu) with a step-down entrypoint (`GOSU_USER`/`GOSU_CHOWN` env vars).

## Commands

```bash
make build                                  # build jahrik/arm-gosu:latest
docker run --rm -e GOSU_USER=nobody:nogroup jahrik/arm-gosu:latest id -un
```

## CI

`build.yml`: Test (build + step-down check) on PR; Release (buildx amd64/arm64/armv7 push to Docker Hub) on merge to main. Needs `DOCKERHUB_USERNAME`/`DOCKERHUB_TOKEN` secrets.

## Quirks

- `docker-entrypoint.sh` is vendored from gisjedi/gosu-entrypoint — keep attribution header.
- gosu comes from Ubuntu's apt repo (unpinned; hadolint DL3008 ignored on purpose).
- Base-image repo: no compose, no swarm stack.
