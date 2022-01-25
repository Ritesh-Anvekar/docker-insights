# **Docker Insights**
<img src="./hello-from-alpine/pic/docker.ico" width="200" height="200" />

## References 
+ [Docker Overview](https://docs.docker.com/get-started/overview/)
+ [Install Docker Desktop on Windows](https://docs.docker.com/desktop/windows/install/)
+ [Install WSL](https://docs.microsoft.com/en-us/windows/wsl/install)

<br>
<br>
<br>
<br>
<br>

# Host Information [in my case it's Laptop]
## Windows Specs
+ Edition	Windows 10 Home
+ Version	21H1
+ OS build	19043.1466
+ Serial number	MP1NKND5
+ Experience	Windows Feature Experience Pack 120.2212.3920.0

<br>

## WSL 2 Backend (Windows Subsystem for linux Update v2) <img src="./hello-from-alpine/pic/wsl.png" width="60" height="60" /> <br>

> <img src="./hello-from-alpine/pic/ubuntu.png" width="50" height="50" /> <br>
> <img src="./hello-from-alpine/pic/ubuntu-OS-Release.png" width="775" height="289" />
<br>

## Docker Desktop 
<img src="./hello-from-alpine/pic/dockerDesktop.png" width="900" height="627" /> <br>
<br>
> Additional Version Insights <br> <br>
> <img src="./hello-from-alpine/pic/docker version.png" width="850" height="526" /> <br>
> <br> 

<br>

### Docker Information <br><br>
<img src="./hello-from-alpine/pic/docker info.png" width="924" height="1045" />

<br>

# Docker Hub
<img src="./hello-from-alpine/pic/dockerHub-Explore.png" width="948" height="603" /> <br>
<br>
> <img src="./hello-from-alpine/pic/dockerHub-Repositories.png" width="910" height="1007" />

<br>
<br>
<br>
<br>
<br>

# QUICK ILLUSTRATION OF DOCKER TUTORIAL EXAMPLE
## References
+ [Docker > Orientation and setup](https://docs.docker.com/get-started/)
+ [Docker Hub > Explore > docker/getting-started](https://hub.docker.com/r/docker/getting-started)

```
docker run -d -p 8080:80 --name docker-tutorial docker/getting-started
```
On successful execution of the above docker command, <br>
It should print "Container ID" in the last line, something like 76216cdc5d829f5c3efbbec1f6e2af55fc5df14bc7c3ef3f1a65ca4d01f86f60.

## Execution Snapshot & Walk Thro' <br>
> <img src="./hello-from-alpine/pic/docker-tutorial-executionSnap.png" width="976" height="252" /><br><br>
> Let's walk-thro these flags, options, args, etc.. <br>
>
> ```run``` <br>
> - it first creates a write-able container layer over the specified image, and then starts it using the specified command.
> - for more info, click [here](https://docs.docker.com/engine/reference/commandline/run/)
>
> ```-d``` <br>
> - runs the container in detached mode (in the background)
> - for more info, click [here](https://docs.docker.com/engine/reference/run/#detached--d)
>
> ```--name docker-tutorial``` <br>
> - name of the container
>
> ```-p 8080:80``` <br>
> - map port 8080 of the host to port 80 in the container
>
> ```docker/getting-started``` <br>
> - the image to use
> <br>

<br>

## Docker Dashboard <br>
## One should be able to see the above ``[run]`` container in here, as seen below :) <br> 
> <img src="./hello-from-alpine/pic/dockerDash.png" width="1025" height="597" /><br> <br>
> ## &nbsp; &nbsp; Furthermore on clicking option 'Open in Browser', one should be navigated as seen below ...
>> <img src="./hello-from-alpine/pic/docker-tutorial-on-localhost-8080.png" width="1205" height="482"/> <br> <br>






<br>
<br>
<br>
<br>
<br>

# USAGE & ILLUSTRATION OF BASIC DOCKER COMMANDS
## References
+ [Docker CLI - Base Commands](https://docs.docker.com/engine/reference/commandline/docker/)

<br><br>

# **[build] & [run]**

# Firstly, Let's see how one can **[build]** an Image using 'Dockerfile'.
<img src="./hello-from-alpine/pic/docker-image.png" width="200" height="200" /> <br>
### In order to build image, we need an simple text file strictly named as "Dockerfile". <br>
### let's say this Dockerfile holds below lines .. <br>
+ FROM alpine <br>
+ CMD ["/bin/sh", "-c", "echo '...hello from alpine container, It works!'"] <br>
<br>

```
docker build -t image-hellofromalpine:tag-v1.0 hello-from-alpine/
```

### On successful execution of the above docker command, <br>
### It should print in the last line, something like  => => naming to docker.io/library/hello-from-alpine:1.0. <br> <br>

## Execution Snapshot & Walk Thro' <br>
> <img src="./hello-from-alpine/pic/hellofromalpine-build-executionSnap.png" width="130" height="130" />
> <br> <br>
> Let's walk-thro these flags, options, args, etc.. <br>
>
> ```build``` <br>
> - Build an image from a Dockerfile
> - for more info, click [here](https://docs.docker.com/engine/reference/commandline/build/)
>
> ```-t image-hellofromalpine:tag-v1.0 hello-from-alpine/```<br>
> - Name and optionally a tag in the 'name:tag' format 
> - Location of Docker File, in this case it's ```hello-from-alpine``` folder residing within project folder 'docker-insights' 
> <br>

<br> <br>
# Now let's create & start a Container for the above built Image [```image-hellofromalpine:tag-v1.0```] using **[run]** command. 
<img src="./hello-from-alpine/pic/docker-container.png" width="200" height="200" />

```
docker run --name container-hellofromalpine image-hellofromalpine:tag-v1.0
```

### On successful execution of the above docker command, <br>
### It should print something like &nbsp; &nbsp; &nbsp; &nbsp; ......hello from alpine container, It works!

<br>

## Execution Snapshot & Walk Thro' <br>
> <img src="./hello-from-alpine/pic/hellofromalpine-run-executionSnap.png" width="130" height="130" />
> <br> <br>
> Let's walk-thro these flags, options, args, etc.. <br>
>
> ```run``` <br>
> - it first creates a write-able container layer over the specified image, and then starts it using the specified command.
> - for more info, click [here](https://docs.docker.com/engine/reference/commandline/run/)
>
> ```--name container-hellofromalpine``` <br>
> - name of the container
>
> ```image-hellofromalpine:tag-v1.0```<br>
> - the image to use
> <br>

<br> <br>


# Let's see how one can **[build]** an Image using on-the-fly 'Dockerfile'.
<img src="./hello-from-alpine/pic/docker-image.png" width="200" height="200" /> <br>
```
docker build -t image-hellofromalpine-fly:tag-v1.0 - << EOF
FROM alpine:latest
CMD ["/bin/sh", "-c", "echo '...hello from alpine container (build by on-the-fly Dockerfile), It works!'"]
EOF
```

### On successful execution of the above docker command, <br> 
### It should print in the last line, something like  => => naming to docker.io/library/image-hellofromalpine-fly:tag-v1.0. <br><br>

## Execution Snapshot & Walk Thro' <br>
> <img src="./hello-from-alpine/pic/hellofromalpine-fly-build-executionSnap.png" width="130" height="130" />
> <br> <br>
> Let's walk-thro these flags, options, args, etc.. <br>
>
> ```build``` <br>
> - Build an image from a Dockerfile
> - for more info, click [here](https://docs.docker.com/engine/reference/commandline/build/)
>
> ```-t image-hellofromalpine-fly:tag-v1.0```<br>
> - Name and optionally a tag in the 'name:tag' format 
>
> ```- << EOF``` <br>
```FROM alpine:latest ``` <br>
```CMD ["/bin/sh", "-c", "echo '...hello from alpine container (build by on-the-fly Dockerfile), It works!'"]``` <br>
```EOF```
> - On the fly Dockerfile.

<br> <br>
# Now let's create & start a Container for the above built Image [```image-hellofromalpine-fly:tag-v1.0```] using **[run]** command. 
<img src="./hello-from-alpine/pic/docker-container.png" width="200" height="200" />

```
docker run --name container-hellofromalpine-fly image-hellofromalpine-fly:tag-v1.0
```

### On successful execution of the above docker command, <br>
### It should print ......hello from alpine container (build by on-the-fly Dockerfile), It works! <br><br>

## Execution Snapshot <br>
> <img src="./hello-from-alpine/pic/hellofromalpine-fly-run-executionSnap.png" width="130" height="130" /> <br><br>

<br>

<hr>

#### Few other command w.r.t Images & Container.
+ docker image ls 
+ docker image inspect <ImageName:Tag>
+ docker rmi <ImageName:Tag>
+ docker container ls
+ docker container inspect <ContainerName|ContainerID>
+ docker stop <ContainerName|ContainerID>
+ docker rm <ContainerName|ContainerID>

<br><br>

# Watch this space for more... 
# **[network]**
<img src="./hello-from-alpine/pic/docker-network.png" width="170" height="118" /><br><br>

<br><br>

## References 
+ [xxxxxxxxx](https://x)
+ [xxxxxxxxx](https://x)

<br>
<br>
<br>
<br>
<br>

# **[volume]**
<img src="./hello-from-alpine/pic/docker-volume.png" width="175" height="165" /><br><br>

<br><br>

## References 
+ [xxxxxxxxx](https://x)
+ [xxxxxxxxx](https://x)

<br>
<br>
<br>
<br>
<br>

# **[compose]**
<img src="./hello-from-alpine/pic/docker-compose.png" width="200" height="200" /><br><br>

<br><br>

## References 
+ [xxxxxxxxx](https://x)
+ [xxxxxxxxx](https://x)

<br>
<br>
<br>
<br>
<br>

# **Dockerized JavaScript App with Mongo DB**  
<img src="./hello-from-alpine/pic/js.png" width="1280" height="720" />

## Localised Run <br> <br>


## Dockerized Run - with & without docker-compose <br> <br>

<br><br>

## References 
+ [Docker Samples](https://docs.docker.com/samples/)
+ [Docker - Dev Best Practices](https://docs.docker.com/develop/dev-best-practices/)
+ [Docker - Resources](https://docs.docker.com/get-started/resources/)
+ [Docker - ACI Integration](https://docs.docker.com/cloud/aci-integration/)



<br><br>

## References 
+ [xxxxxxxxx](https://x)
+ [xxxxxxxxx](https://x)

<br>
<br>
<br>
<br>
<br>

# Kubernetes
<img src="./hello-from-alpine/pic/kubernetes.png" width="130" height="130" />

> Enable Single Node Cluster

> Alternatively, we have minikube :)

> Monitoring
>> Kubernetes Dashboard 
>> Prometheus - Grafana


<br><br>

## References 
+ [xxxxxxxxx](https://x)
+ [xxxxxxxxx](https://x)

<br>
<br>
<br>
<br>
<br>

# GitOps Principles
<img src="./hello-from-alpine/pic/gitops.png" width="250" height="140" />

> [What is GitOps ?](https://about.gitlab.com/topics/gitops/)


<br><br>

## References 
+ [xxxxxxxxx](https://x)
+ [xxxxxxxxx](https://x)

<br>
<br>
<br>
<br>
<br>

# GitHub / GitLab / Azure Git
<img src="./hello-from-alpine/pic/github.png" width="128" height="128" />
<img src="./hello-from-alpine/pic/gitlab.png" width="128" height="128" />
<img src="./hello-from-alpine/pic/azureGitRepo.png" width="128" height="128" />

<br><br>

## References 
+ [xxxxxxxxx](https://x)
+ [xxxxxxxxx](https://x)

<br>
<br>
<br>
<br>
<br>

# ArgoCD Application
<img src="./hello-from-alpine/pic/argocd.png" width="150" height="150" />
>

<br><br>

## References 
+ [xxxxxxxxx](https://x)
+ [xxxxxxxxx](https://x)


<br>
<br>
<br>
<br>
<br>

# Additional Subjects
[Java Debugging Intellij](https://training.play-with-docker.com/java-debugging-intellij/) <img src="./hello-from-alpine/pic/intellij.png" width="25" height="25" />


