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
    image: ghcr.io/applicreation/harmony-proxy:latest
    ports:
      - 80:80
  core:
    image: ghcr.io/applicreation/harmony-core:latest
    volumes:
      - ./.harmony/core:/root/.harmony:ro
  example:
    image: ghcr.io/applicreation/harmony-module-example:latest
```

```yaml
# ./.harmony/core/config.yaml
---

name: Example
modules:
  - name: Example
    url: /example
```

## Development

```shell
docker compose up
```
