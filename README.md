# JHipster-onbuild image

## Usage

1) Add one of those magic `Dockerfile` at the root of your JHipster project:

### **One stage build** (produce a large docker image >1.8GB)**
```
FROM pbesson/jhipster:onbuild
```
### **Multi stage build** (produce a small docker image ~140MB) and require that your docker daemon support [multistage builds](https://docs.docker.com/engine/userguide/eng-image/multistage-build/)
```
FROM pbesson/jhipster:onbuild
FROM pbesson/jhipster:onrun
```

2) Run:
```
docker build -t your-docker-image-name .
```

## (Optional) Building the onbuild images

1) Build the jhipster-onbuild docker image:
```
docker build -t pbesson/jhipster:onbuild -f Dockerfile-onbuild .
```
2) Build the jhipster-onrun docker image:
```
docker build -t pbesson/jhipster:onrun -f Dockerfile-onrun .
```