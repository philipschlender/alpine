# Alpine

## Introduction

Alpine is a docker image based on [Alpine](https://www.alpinelinux.org/). It includes some handy additions like basic packages, preset time zone and user.

## How to use

### Build

```bash
docker build --file docker/Dockerfile --tag philipschlender/alpine:latest .
```

### Run

```bash
docker run --detach --name alpine --rm philipschlender/alpine:latest
```

### Exec

```bash
docker exec --interactive --tty alpine bash
```

### Stop

```bash
docker stop alpine
```
