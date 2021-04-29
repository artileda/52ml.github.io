# Buildah: An alternative containerization tool

Docker somewhat became trendsetter for containerization technology alongside with Kubernetes (k8s, for short).
Docker and K8s are tool for serving containerization but had fundamental different. Docker job is do application containerization that isolate application with host system when Kubernetes is abstracting many machine to do containerization and manage container execution (orchestration).

## What is Buildah

Buildah is new kid on the block from Red Hat, A tool for creating containers (superset of docker functionality) and work well with K8s (thank CRI-O).

Bulidah had sibling : Podman and Skopeo (you can call it, the Trinity of Container). Those sibling provide complementary work for Buildah.

- Buildah : Building the container
- Podman : Running the container
- Skopeo : Transfering the container

Buildah work by using terminal command, lets took example from this Dockerfile

```docker
from scratch
```

to do than in Buildah, you run on terminal

```sh
buildah from scratch
```
or 

Run the Dockerfile directly using Buildah, since Buildah support Dockerfile configuration.

## Why RedHat brought those three kid to World

The main reason is to make containerization less bloat and more secure, so Red Hat come with solution to bring up Buildah, Podman and Skopeo. Those giving functionality like Docker in rootless and daemonless manner. 

Rootless meaning you not need any superuser access to work with your container tool, which improve you security by reducing attack vector to pwning you device.

You don't need create or export container functionality in single application while running container in production, Red Hat said let split this up to piece then it turn to those Trinity of Container.

Daemonless, making you device less running any daemon who possesing you memory and resources of your device.

## The Basic

Time to taste buildah, [you need install it first](https://github.com/containers/buildah/blob/master/install.md).

1. Grabbing image 
    ```
    buildah pull [image name]
    ```

2. Seeing all image 
    ``` 
    buildah list
    ```

3. Creating container from image
    ```
    buildah from [image name]
    ```

4. Renaming the container
    ```
    buildah rename [old name] [new name]
    ```

5. Mounting filesystem container
    ```
    buildah mount [container name]
    ```
6. Unmounting filesystem container
    ```
    buildah unmount [container name]
    ```
7. To see all available options
    ```
    buildah help
    ```

Remember, Buildah just work for building contianer as it name.

[Click here If you want to learn more about The Trinity of Containers.](http://redhatgov.io/workshops/containers_101/)
