# Debian-based base Dev Containers

A Debian-based Dev Container image with batteries included, similar to the
upstream universal image for language tooling used in different projects here
at Recap Time Squad and beyond.

Currently building against the latest Debian release with lead time of at least
3-6 months on the next stable release.

## Usage

* On your `devcontainer.json`:

```json
{
  "image": "ghcr.io/recaptime-dev/devenvkit/base/debian:latest"

  // other configs here
}
```

* Or in your Dockerfile:

```dockerfile
# syntax=docker/dockerfile:labs
FROM ghcr.io/recaptime-dev/devenvkit/base/debian:latest
```
