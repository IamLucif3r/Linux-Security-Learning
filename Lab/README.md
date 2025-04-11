# DAY-ZERO-LAB

This repository consists of a dockerfile, which can be used to learn the Linux Security and it's fundamentals. 


### How to build the Dockerfile ?

It is recommended to run the lab using `runcvm` runtime. Install [runcvm](https://github.com/newsnowlabs/runcvm) runtime to run your docker container with a separate container. Think of it as a VM running in docker.

To build docker image : `docker build -t day-zero-lab .`

### How to run the docker container ?

To run your lab use:

```bash
docker run -d \
  --runtime=runcvm \
  --name devlab \
  -p 8080:8080 \
  -v $(pwd)/workspace:/home/developer/workspace \
  day-zero-lab
```

This will boot up a docker container with separate kernel and a code-server, which can be accessed over port `:8080`.
