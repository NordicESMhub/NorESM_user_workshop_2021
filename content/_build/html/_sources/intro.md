# Running NorESM in a container

![](/paul-teysen-bukjsECgmeU-unsplash.jpg)

## What is a container?

A **container** is a unit of software that bundles a code and all its dependencies so that an application can run quickly in various computing environments

A container **image** is a standalone, executable package of software which includes everything needed to run an application: source code, compilers, libraries, etc.

Images *become* containers **at runtime** when they run on a container engine (like Docker, Singularity, etc.) 

*(From [https://www.docker.com/resources/what-container](https://www.docker.com/resources/what-container))*

## Docker <img src="https://www.docker.com/sites/default/files/d8/styles/role_icon/public/2019-07/Docker-Logo-White-RGB_Vertical-BG_0.png?itok=8Tuac9I3" height="40">

 
Docker is probably the most popular platform for creating and distributing container images

It is very easy to install (especially on Linux machines) and well documented

<img src="https://www.docker.com/sites/default/files/d8/styles/large/public/2018-11/container-what-is-container.png?itok=vle7kjDj" height="300">

:::{note}
Containers isolate applications from their environment
:::

## Docker for everything? <img src="https://w7.pngwing.com/pngs/636/195/png-transparent-warning-sign-traffic-sign-hazard-warning-signs-text-logo-copyright-thumbnail.png" height="40">

Docker works well for local or **private** resources, and 

- [x] it is great to **develop** and **share** ([Docker-hub](https://hub.docker.com))

- [x] Docker images are built layer by layer from a *recipe* called Dockerfile, and should something fail in a particular layer, one can just fix it and resume the build from where it stopped

however, Docker is

- [ ] not suitable for **multi-user** environments like High Performance Computers (HPC) because processes within the Docker container are executed with root privileges

and therefore no *sensible* **HPC** centers will allow it

## Singularity <img src="https://sylabs.io/assets/svg/singularity-logo.svg" height="40">

Compared to Docker, Singularity exhibits several features which make it more suitable for use on HPC, and in particular:

- [x] there is **no privilege** escalation inside Singularity containers (user outside == user inside)

- [x] it does not requires any system changes for **HPC**

- [x] it provides a simple integration with **resource managers** (like Slurm)

Also, from the user point-of view:

- [x] Singularity uses a single-file based container format (**SIF™** = Singularity Image File)

- [x] it supports multiple **architectures** (x86-64, PPC, <img src="https://www.arm.com/-/media/global/logos/Arm-logo-reverse-white.svg?h=175&w=300&hash=F5A828FC9C66575A911DF0B5CB3D04B4E8E5DC50&hash=F5A828FC9C66575A911DF0B5CB3D04B4E8E5DC50" height="25">)

however

- [ ] building container images from a Singularity definition file (.def) is tedious (although the content is *similar* to that of a Dockerfile)

- [x] it is possible to convert a Docker image into Singularity

- [x] the size of a Singularity Image File is significantly smaller than the *equivalent* Docker image archive
