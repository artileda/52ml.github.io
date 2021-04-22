# Buildah: An alternative containerization tool

Docker is somewhat became trendsetter for containerization technology alongside with Kubernetes (k8s, for short).
Docker and K8s the is tool for serving containerization but had fundamental different, Docker job is do application containerization than isolate app with host system when Kubernetes is abstracting many machine to do containerization and manage container execution.

## What is Buildah

Buildah is new kid on the block from Red Hat which contain superset of Docker functionality for creating containers and work well with K8s (thank CRI-O Standard).

Bulidah had sibling : Podman and Skopeo (you can call it, the Trinity of Container). Those sibling provide complementary work for Buildah.

- Podman : Running the container
- Skopeo : Transfer container images

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

Remember Buildah just work for building contianer as it name.
