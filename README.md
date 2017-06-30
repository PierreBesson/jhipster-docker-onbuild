# JHipster-onbuild image

## Usage

1) Add either [Dockerfile-one-stage](Dockerfile-one-stage) or [Dockerfile-multi-stage](Dockerfile-multi-stage) (if your docker daemon support [multistage builds](https://docs.docker.com/engine/userguide/eng-image/multistage-build/)) as `Dockerfile` at the root of your JHipster project

2) Run:
```
docker build -t your-docker-image-name .
```

## Building

1) Build the jhipster-onbuild docker image:
```
docker build -t pbesson/jhipster:onbuild -f Dockerfile-onbuild .
```
2) Build the jhipster-onrun docker image:
```
docker build -t pbesson/jhipster:onrun -f Dockerfile-onrun .
```

Notes:
docker image 1 stage: 1.82GB
docker image multi-stage: 139MB
