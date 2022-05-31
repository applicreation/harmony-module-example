# harmony-module-example

## Details

This is an example module to be used with Harmony.

## Prerequisites

The only tool required is [Docker Desktop](https://www.docker.com/products/docker-desktop).

## Usage

```yaml
# docker-compose.yaml
---

services:
  proxy:
    image: ghcr.io/applicreation/harmony-proxy:v0
    ports:
      - 80:80
  core:
    image: ghcr.io/applicreation/harmony-core:v0
    volumes:
      - ./.harmony/core:/root/.harmony:ro
  example-html:
    image: ghcr.io/applicreation/harmony-module-example-html:v0
```

```yaml
# ./.harmony/core/config.yaml
---

modules:
  - id: example-html
```

## Development

```shell
docker compose up
```
