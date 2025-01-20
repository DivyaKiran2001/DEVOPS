# Jenkins Pipeline for Java based application using Maven, SonarQube, Argo CD, Helm and Kubernetes

![Screenshot 2023-03-28 at 9 38 09 PM](https://user-images.githubusercontent.com/43399466/228301952-abc02ca2-9942-4a67-8293-f76647b6f9d8.png)



# Comparison of Legacy Jenkins and Modern Jenkins with Docker

This document compares the traditional Jenkins architecture (Master and Worker Nodes) with the modern approach using Docker and containers.

## Table of Comparison

| **Aspect**            | **Legacy Jenkins (Master and Worker Nodes)**                                    | **Modern Jenkins (Docker and Containers)**                         |
|-----------------------|-------------------------------------------------------------------------------|-------------------------------------------------------------------|
| **Architecture**       | Master node manages jobs and distributes tasks to static worker nodes.         | Jenkins master runs in a Docker container; worker nodes are dynamically provisioned as containers. |
| **Setup**              | Requires manual setup of master and worker nodes on separate machines.         | Jenkins setup is streamlined with Docker images (`jenkins/jenkins`). |
| **Scalability**        | Adding new worker nodes requires configuring physical/virtual machines.        | Worker nodes are provisioned as containers dynamically, ensuring scalability. |
| **Build Environment**  | Static environments; configurations persist across builds.                    | Ephemeral containers ensure a clean environment for each build.  |
| **Isolation**          | Limited isolation; builds can leave residual data on nodes.                   | Containers provide complete isolation between builds.            |
| **Maintenance**        | Manual updates and configuration for master and worker nodes.                 | Easier maintenance with Docker images and container orchestration. |
| **Real-Time Example**  | - Master node orchestrates jobs.<br> - Worker nodes are separate machines for Windows, Linux, and Mac builds. | - Master node runs in Docker.<br> - Worker nodes are spawned dynamically for builds (e.g., Node.js, Python, Java). |
| **Pipeline Example**   | - Manual configuration of build environments on worker nodes.<br> - Build/test on static nodes. | - Use `Jenkinsfile` to define pipelines.<br> - Docker containers handle builds, tests, and deployments. |
| **Cost Efficiency**    | Requires dedicated resources for worker nodes, even when idle.                | Containers are lightweight, consuming resources only during builds. |
| **Key Tools**          | SSH, static nodes, and physical/virtual machines.                             | Docker, Docker-in-Docker (DinD), Kubernetes for orchestration.    |
| **Command Example**    | - Configure master and workers manually.<br> - Jobs run on specific worker nodes. | - Run Jenkins master: <br> `docker run -d -p 8080:8080 jenkins/jenkins:lts` <br> - Dynamic workers: <br> `docker run -d jenkins/agent` |

---

## Real-Time Examples

### Legacy Jenkins
A software development company builds applications for multiple platforms:
1. **Master Node**:
   - Hosts Jenkins UI and manages pipelines.
2. **Worker Nodes**:
   - Separate machines for Windows, Linux, and Mac environments to build and test platform-specific applications.

### Modern Jenkins with Docker
A company leverages Docker to simplify CI/CD pipelines:
1. **Master Node**:
   - Runs as a Docker container using the `jenkins/jenkins` image.
2. **Dynamic Worker Nodes**:
   - Spun up as containers on demand for builds (e.g., Python, Node.js, Java).
3. **Pipeline**:
   - Developers push code to GitHub.
   - Jenkins triggers pipelines and spawns containers to:
     - Run tests.
     - Build Docker images.
     - Deploy artifacts.

---

## Key Benefits of Modern Jenkins with Docker
1. **Reproducibility**: Every build gets a clean, isolated environment.
2. **Scalability**: Containers can be dynamically added or removed.
3. **Ease of Maintenance**: Docker images simplify updates and dependency management.
4. **Cost Efficiency**: Containers only use resources during builds.

---

## Commands for Setting Up Jenkins with Docker

### Run Jenkins Master
```bash
docker run -d -p 8080:8080 -p 50000:50000 --name jenkins-master jenkins/jenkins:lts




