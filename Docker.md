# Docker

- Learning Link - https://www.youtube.com/watch?v=exmSJpJvIPs&t=3s

## Basics 
- Docker is super important for anyone who is working in IT industry because it eases the deployment process.
- Docker is a platform that helps us build containers. There are two basic terms in docker i.e. **Docker Container** & **Docker Image**. **Docker Container** is a single bundle/unit wherein we are packing our application with its dependencies.
- Physical Machine: A real, dedicated computer/server with its own hardware. Runs directly on hardware (no abstraction layer). One OS per machine. High performance (no overhead). Expensive and less flexible
- Virtual Machines: A software-based “computer” running on top of a physical machine using a hypervisor. Each VM has its own OS (heavy). Uses a hypervisor like VMware or VirtualBox. Strong isolation. Slower than physical machines (due to overhead). More flexible than physical machines.
- Containers: Lightweight environments that package applications with dependencies, sharing the host OS. No separate OS per container (very lightweight). Fast startup (seconds or less). Uses container engines like Docker. Less isolation than VMs (but usually sufficient). We can create containers on top of VMs and Physical Servers. Docker can also run on a VM and Physical server. 
- Now-a-days, Docker is mostly created on VMs or EC2 machines. Containers are light-weight . Docker Containers do not have the complete operating systems. Containers use the resources from the host operating systems. Container has the base image of the operating system. A Docker Container is a package and it is a combination of your applications + application libraries + system dependencies. 
- Docker containers are easy to ship or deploy to another servers. They use the resources from the base operating system or from the operating system on which they are running. 
- Docker Containers - Base Image of operating system or very minimum amount of operating system packages + application + application libraries. Docker is a containarization platform. Simply, write a "DockerFile" and using docker commands submit it to docker engine/platform. Docker engine will convert the DockerFile into a Docker Image / Docker Container and finally using some Docker Commands we can convert it into Container.
- LifeCycle for Docker ==> DockerFile => Image => Container.

- Container are portable. We share the docker image when we share the container. Docker container is light-weight in nature. Its size is quite less.

- A Docker image is a lightweight, standalone package that contains everything needed to run an application, including code, libraries, dependencies, and configuration files. It is immutable, meaning once created, it does not change, ensuring consistency across environments. Docker images are used to create containers, which are runnable instances of those images. They are built using a Dockerfile and can be shared via repositories like Docker Hub. This makes deployment faster, scalable, and consistent across development, testing, and production environments. Docker Image is kind of an executable file. It has instructions to build the container. Docker image helps us create multiple containers. When we create a container from an image, the whole environment setup is created inside the container and the container uses the computer resources.

- Following are the basic docker commands -
  - docker pull IMAGE_NAME
  - docker images
  - docker run IMAGE_NAME - Execute or create a container from the docker image
  - docker run -it IMAGE_NAME - "-it" enables the container to run in an interactive mode
  - docker stop CONT_NAME or  CONT_ID
  - docker start CONT_NAME or  CONT_ID
  - docker ps -a - This command is used to check the list of containers which we have
  - docker ps - This command is used to check the list of running containers
  - Command to remove the image - docker rmi DOCKER_IMAGE_NAME
  - Command to remove the container - docker rm CONT_NAME
  - Command to run the container in the background mode - docker run -d IMAGE_NAME
  - By default all the containers run in attach mode. 
  - Create container by custom name = docker run -d IMAGE_NAME --name MyCustomName


### 🔹 What are Docker Image Layers?

* A Docker image is built as a **stack of layers**, where each layer represents a change to the filesystem.
* These changes come from instructions in a **Dockerfile** such as `FROM`, `RUN`, `COPY`, `ADD`, etc.

### 🔹 How Layers are Created

* Each instruction in the Dockerfile creates a **new layer**.
* Example:

  * `FROM ubuntu` → base layer
  * `RUN apt-get install python` → new layer added
  * `COPY . /app` → another layer added
* These layers are stacked sequentially to form the final image.

### 🔹 Immutable Nature

* Layers are **read-only (immutable)** once created.
* If you modify something, Docker does not change the existing layer—it **creates a new layer** on top.

### 🔹 Layer Caching (Performance Boost)

* Docker caches layers during build.
* If a layer hasn’t changed, Docker reuses it instead of rebuilding.
* This significantly **speeds up image builds**.
* Example: If only your application code changes, earlier layers (like installing dependencies) are reused.

### 🔹 Layer Reusability (Storage Efficiency)

* Layers can be **shared across multiple images**.
* If multiple images use the same base image (e.g., Ubuntu), they reuse those layers.
* This reduces **disk usage** and improves **download efficiency**.

### 🔹 Union File System

* Docker uses a **union filesystem** (like OverlayFS) to combine all layers into a single unified view.
* Even though layers are separate, they appear as one complete filesystem inside the container.

### 🔹 Copy-on-Write Mechanism

* When a container runs, Docker adds a **writable layer on top** of the image layers.
* Any changes made during runtime go into this top layer.
* Original image layers remain unchanged.

### 🔹 Layer Order Matters

* Layers are built and applied **top to bottom**.
* Frequently changing instructions should be placed **later** in the Dockerfile to maximize caching.

### 🔹 Key Benefits

* Faster builds (due to caching)
* Efficient storage (layer sharing)
* Consistency across environments
* Easy rollback (reuse previous layers)



