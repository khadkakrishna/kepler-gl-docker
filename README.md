# kepler-gl-docker

<p float="left">
<img width="130" alt="Kepler.gl" src="./_images/kepler.gl-logo.png" hspace="20"> 
<img width="120" alt="Kepler.gl" src="./_images/docker-logo.png" hspace="20">
</p>

This code deploys kepler.gl [demo-app](https://github.com/keplergl/kepler.gl/tree/master/examples/demo-app) in docker container


![](./_images/landing-page.png)


## Run the application using *docker compose*
1. Update the `MapboxAccessToken` in [.env](./env) (it is not necessary to have token to start the application).
2. Change the `KEPLER_PORT` in [.env](./env) if 8080 port is not available to use.
3. Run `docker compose up -d` to start the application, it will pull the image and run the application on [http://localhost:8080](http://localhost:8080) or `http://localhost:<KEPLER_PORT>/` if port is changed.
4. To stop and remove the container run `docker compose down`


## Run the application using *docker run*

1. Pull the image using following command
```bash
docker pull krishnakhadka/kepler-gl:latest
```

2. Run the container 
```bash
docker run --name kepler-gl -p 8080:8080 -d krishnakhadka/kepler-gl:latest
```

3. Provide MapboxAccessToken in the run command (if available)
```bash
docker run --name kepler-gl -p 8080:8080 -e MapboxAccessToken="GeneratedMapboxAccessToken" -d krishnakhadka/kepler-gl:latest
```

## Build the application from *Dockerfile*
Following command can be used for building the image 
```bash
docker build -t krishnakhadka/kepler-gl https://github.com/khadkakrishna/kepler-gl-docker.git
```
