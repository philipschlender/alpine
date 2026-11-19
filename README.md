# Alpine

## Introduction

Alpine is a docker image based on [Alpine](https://alpinelinux.org/). It includes some handy additions like basic packages, preset time zone and user.

## How to use

### Build

```bash
docker build --file docker/Dockerfile --tag philipschlender/alpine:latest .
```

### Run

```bash
docker run --interactive --name alpine --rm --tty philipschlender/alpine:latest
```

### Push

```bash
docker push philipschlender/alpine:latest
```
