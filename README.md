# CI-CD-Pipeline
Real time webapp deployment on Kubernetes cluster using Jenkins CI/CD pipeline.

# INTRODUCTION TO DOCKER
Docker is an open platform for developing, shipping, and running
applications. Docker enables you to separate your applications from your
infrastructure so you can deliver software quickly. Docker is a software
platform that allows you to build, test, and deploy applications quickly.
Docker packages software into standardized units called containers that
have everything the software needs to run including libraries, system tools,
code, and runtime.Docker registries are used to host and distribute Docker
Images. Docker Hub is Docker's official cloud-based registry. The free
version of Docker Hub allows for one private repository. Nonpaying
users are otherwise restricted to public repositories.
.

![112](https://user-images.githubusercontent.com/78873371/219970678-2ff8f90f-1ffa-4d8a-9739-4fa6df6f4945.jpg)

# PROJECT DESCRIPTION
1. JENKINS
2. ANSIBLE
3. WEBAPP(Kubernetes cluster)

# WORKING

Firstly, developer writes the Docker File and push it to GITHUB Repository.
If the git repository gets new commit, it will notify Jenkins through
WEBHOOK to build that new code.
JENKINS will PULL all the code from repository and SSH (secure shell) to
the ANSIBLE SERVER in order to provide network communication and
share data.
ANSIBLE SERVER will firstly get the DockerFile and start build Image.
Then, tag image and push it to DOCKER HUB.
Ansible server will then SSH to KUBERNETES SERVER.
Thereafter, Fetch the LATEST IMAGE which is just build and pushed. PULL
from DOCKER HUB and build container from Image.
This container must be accessible to us using IP and Port by writing
service.mk in Kubernetes Cluster.
A Kubernetes cluster is a set of nodes that run containerized
applications. Containerizing applications packages an app with its
dependences and some necessary services. They are more lightweight
and flexible than virtual machines.
Also, we maintain a image version as well as Separate latest Image with
Build Number.

# DevOps Tools- 
## JENKINS
A DevOps software development method called continuous integration
involves developers regularly merging their code changes into a common
repository, which is followed by the execution of automated builds and
tests. Developers frequently utilise Jenkins, an Open-Source Continuous
Integration (CI) tool, to automate the testing and deployment of their apps.
A Webhook is a tool that enables a Jenkins project to be built automatically
in response to a commit that is pushed to a Git repository.
![113](https://user-images.githubusercontent.com/78873371/219970711-b3514dc6-4a01-44ef-93f1-16c978fa0786.jpg)

## ANSIBLE
Ansible is defined as an open-source, cross-platform tool for resource
provisioning automation that DevOps professionals popularly use for
continuous delivery of software code by taking advantage of an
“infrastructure as code” approach.
![114](https://user-images.githubusercontent.com/78873371/219970728-e8abf54e-ec28-485a-9b41-57d9ad37ea33.jpg)

## GITHUB
GitHub offers an end-to-end DevOps platform with cloud-hosted Git
services—i.e., source code management (SCM) and versioning control.
GitHub also includes project management, CI/CD, automation,
enterprise-grade security scanning, and more to serve all software
development needs
.GitHub has always made it easy for developers to move back and forth
between public/private development modes
![115](https://user-images.githubusercontent.com/78873371/219970747-7581c086-ed6e-4449-a198-ebcf2f417e7d.jpg)

# WORKING
1. Jenkins running on a container
![116](https://user-images.githubusercontent.com/78873371/219970787-34bf33a8-eaca-4143-a254-e11ce1266ae4.jpg)
![117](https://user-images.githubusercontent.com/78873371/219970794-65a2dd20-a33b-495c-a98f-2fc0a7a9da09.jpg)

2. Ansible running on a container
![118](https://user-images.githubusercontent.com/78873371/219970802-9d091a84-0f48-4e15-9dc3-e42e6f5b510a.jpg)

3. Single node minikube cluster running on ec2 instance
![119](https://user-images.githubusercontent.com/78873371/219970907-39202046-968a-4597-951c-5afe6de74c3c.jpg)


4. Developer commits and pushes dockerfile to github repository
![120](https://user-images.githubusercontent.com/78873371/219970965-a878a5c3-d767-441f-9966-078df2688848.jpg)

5. Jenkins is notified through WEBHOOK to build that new code.
![121](https://user-images.githubusercontent.com/78873371/219970955-c10ce62a-6a2f-4442-b824-5bd9f6412ba1.jpg)

6. JENKINS will PULL all the code from repository and SSH (secure
shell) to the ANSIBLE SERVER in order to provide network
communication and share data.
![122](https://user-images.githubusercontent.com/78873371/219970981-3b3e1a85-5ab3-4bb4-9e33-f44653c84c81.jpg)

7. Final deployment of website .
![123](https://user-images.githubusercontent.com/78873371/219970984-019628d8-7db4-4e7f-8844-edf6274264c9.jpg)

8. Complete Pipeline
![124](https://user-images.githubusercontent.com/78873371/219970990-cc959a16-b4b2-4243-974e-608c9938df1e.jpg)

