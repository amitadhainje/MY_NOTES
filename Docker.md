# Docker

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

- 