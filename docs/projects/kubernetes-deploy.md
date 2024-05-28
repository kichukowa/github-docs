# Deploying Kubernetes on GCP with CI/CD
By the end of this learning path, participants will have hands-on experience with modern DevOps practices, including version control, infrastructure as code, CI/CD pipelines, containerization, and Kubernetes orchestration.


## Topic 1: Version Control with GitHub

#### Explanation

**Why it's needed**: Version control systems like GitHub are essential for managing changes to code, enabling collaboration, and maintaining a history of project changes.

**Historical Methods**: Earlier methods included manual versioning and centralized systems like SVN, which had limitations in collaboration and version control.

> #### Theory
> 
> **Git Basics**: Understanding repositories, commits, branches, merges, and pull requests.
> 
> **GitHub Features**: Private vs public repositories, collaboration tools, GitHub Actions for CI/CD.

#### Improvements and Modern Methods

**Better Collaboration**: Use of pull requests and code reviews.

**Automation**: Integrating CI/CD pipelines with GitHub Actions.

**Security**: Using branch protection and security policies.

#### Interesting Facts

- Git was created by Linus Torvalds in 2005.
- GitHub hosts over 100 million repositories as of 2024.

#### Quiz

1. What is a Git repository?
2. Explain the difference between git pull and git fetch.
3. What is a pull request?
4. How do you revert a commit in Git?
5. What are GitHub Actions used for?
6. Define branching in Git.
7. What is the purpose of a .gitignore file?
8. How can you protect a branch in GitHub?
9. What command is used to stage changes in Git?
10. Explain the use of forks in GitHub.

#### Additional Tasks

1. Create a new GitHub repository.
2. Make and commit changes to a README file.
3. Create branches and practice merging.
4. Set up branch protection rules.
5. Explore GitHub Actions by creating a simple workflow.


## Topic 2: Infrastructure as Code with Terraform

#### Explanation

**Why it's needed**: IaC allows for the automation and consistency of infrastructure deployment.

**Historical Methods**: Manual configuration and deployment using scripts and CLI commands, which were error-prone and not easily replicable.

#### Theory

**Terraform Basics**: Providers, resources, variables, state management, and modules.

**GKE Deployment**: Setting up GCP provider, creating a GKE cluster, and managing state.

#### Improvements and Modern Methods

**Reusable Modules**: Creating reusable and shareable modules for standard configurations.

**State Management**: Using remote state backends for collaboration.

**Automation**: Integrating Terraform with CI/CD pipelines for continuous deployment.

#### Interesting Facts

- Terraform supports multiple cloud providers including AWS, Azure, GCP, and many others.
- The concept of IaC significantly reduces configuration drift and improves consistency.

#### Quiz

1. What is Infrastructure as Code (IaC)?
2. What is a Terraform provider?
3. How do you define a resource in Terraform?
4. What is Terraform state?
5. Explain the purpose of terraform plan.
6. What is a Terraform module?
7. How can you manage secrets in Terraform?
8. What is the purpose of terraform init?
9. Explain the use of remote backends in Terraform.
10. How does Terraform ensure idempotency?

#### Additional Tasks

1. Set up a basic Terraform configuration for a GKE cluster.
2. Use variables and outputs in your configuration.
3. Explore and use a remote backend for state management.
4. Create a reusable Terraform module.


## Topic 3: Continuous Integration/Continuous Deployment (CI/CD) with GitHub Actions

#### Explanation

**Why it's needed**: CI/CD automates the testing and deployment process, ensuring code is always in a deployable state.

**Historical Methods**: Manual builds and deployments, leading to frequent errors and inconsistent environments.

#### Theory

**CI/CD Basics**: Understanding the principles of continuous integration, delivery, and deployment.

**GitHub Actions**: YAML syntax, jobs, steps, and runners. Creating workflows for CI/CD.

#### Improvements and Modern Methods

**Parallel Jobs**: Running jobs in parallel to speed up the CI/CD process.

**Artifact Management**: Storing and reusing build artifacts.

**Security**: Managing secrets and permissions in workflows.

#### Interesting Facts

- CI/CD pipelines significantly reduce the time to market for new features.
- GitHub Actions allows you to run workflows directly in the cloud without needing your own CI server.

#### Quiz

1. What is CI/CD?
2. Describe the difference between continuous delivery and continuous deployment.
3. What is a runner in GitHub Actions?
4. How do you define a job in a GitHub Actions workflow?
5. Explain the purpose of actions/checkout.
6. What are GitHub Actions secrets?
7. How do you trigger a workflow on push events?
8. What is an artifact in CI/CD?
9. How do you manage dependencies in a CI/CD pipeline?
10. Explain the use of environment variables in GitHub Actions.

#### Additional Tasks

1. Create a simple CI workflow to build and test a project.
2. Set up a CD workflow to deploy an application.
3. Use GitHub secrets to manage sensitive information.
4. Experiment with matrix builds to test across different environments.


## Topic 4: Containerization with Docker

#### Explanation

**Why it's needed**: Containers ensure consistency across development and production environments by packaging applications and their dependencies.

**Historical Methods**: Applications were run directly on the host OS, leading to dependency and environment issues.

#### Theory

**Docker Basics**: Images, containers, Dockerfile, Docker Hub.

**Creating a Dockerfile**: Defining a Dockerfile to build an Nginx server with a static page.

#### Improvements and Modern Methods

**Multi-Stage Builds**: Reducing image size and improving build efficiency.

**Docker Compose**: Managing multi-container applications.

**Security**: Best practices for securing Docker images.

#### Interesting Facts

- Docker was introduced in 2013 and has revolutionized the way applications are deployed.
- As of 2024, Docker Hub hosts millions of container images.

#### Quiz

1. What is Docker?
2. Define an image and a container in Docker.
3. What is a Dockerfile?
4. Explain the purpose of Docker Hub.
5. How do you build a Docker image?
6. What is a multi-stage build?
7. How do you run a Docker container?
8. What is Docker Compose?
9. How can you reduce the size of a Docker image?
10. Explain the concept of container orchestration.

#### Additional Tasks

1. Write a Dockerfile for a simple application.
2. Build and push a Docker image to Docker Hub.
3. Use Docker Compose to manage a multi-container application.
4. Implement best practices for Docker image security.


## Topic 5: Kubernetes Basics and GKE

#### Explanation

**Why it's needed**: Kubernetes automates the deployment, scaling, and management of containerized applications.

**Historical Methods**: Manual container orchestration or using simpler tools like Docker Swarm.

#### Theory

**Kubernetes Concepts**: Pods, nodes, clusters, deployments, services, and ingress.

**GKE**: Google Kubernetes Engine simplifies Kubernetes deployment and management in the cloud.

#### Improvements and Modern Methods

**Autoscaling**: Automatically adjusting the number of pods based on load.

**Stateful Applications**: Managing stateful applications using StatefulSets.

**Security**: Implementing RBAC and network policies.

#### Interesting Facts

- Kubernetes was originally developed by Google and released as open-source in 2014.
- GKE is a managed Kubernetes service that handles cluster management tasks like upgrades and scaling.

#### Quiz

1. What is Kubernetes?
2. Define a Pod in Kubernetes.
3. What is a Kubernetes cluster?
4. Explain the purpose of a Deployment.
5. What is a Service in Kubernetes?
6. How does an Ingress resource work?
7. What is the purpose of a Node in Kubernetes?
8. Describe the concept of autoscaling in Kubernetes.
9. What is a StatefulSet?
10. How does RBAC work in Kubernetes?

#### Additional Tasks

1. Deploy a simple application to a local Kubernetes cluster using Minikube.
2. Create and manage Kubernetes resources like Pods, Deployments, and Services.
3. Explore GKE and deploy a Kubernetes application to it.
4. Implement autoscaling for your application.


## Topic 6: Networking and Ingress in Kubernetes

#### Explanation

**Why it's needed**: Networking in Kubernetes manages communication within the cluster and exposes applications to external traffic.

**Historical Methods**: Manual configuration of networking routes and load balancers.

#### Theory

**Kubernetes Networking**: Services, Ingress controllers, and network policies.

**Ingress Controllers**: Managing external access to services in a Kubernetes cluster.

#### Improvements and Modern Methods

**Service Mesh**: Using tools like Istio for advanced networking features.

**Network Policies**: Implementing fine-grained control over network traffic.

#### Interesting Facts

- Kubernetes uses a flat network model, where all Pods can communicate with each other by default.
- Ingress controllers can manage SSL termination and load balancing.

#### Quiz

1. What is a Service in Kubernetes?
2. Explain the role of an Ingress controller.
3. What is a Network Policy?
4. How does a LoadBalancer service work in Kubernetes?
5. What is the purpose of a ClusterIP service?
6. How can you secure network traffic in Kubernetes?
7. Describe the difference between NodePort and LoadBalancer services.
8. What is SSL termination?
9. How does Kubernetes handle internal DNS resolution?
10. Explain the concept of a service mesh.

#### Additional Tasks

1. Deploy an Ingress controller using Helm.
2. Configure an Ingress resource to route traffic to your application.
3. Implement SSL for your Ingress resource.
4. Explore and implement network policies in your cluster.


## Topic 7: Health Checks in Kubernetes

#### Explanation

**Why it's needed**: Health checks ensure that applications are running correctly and can automatically restart or reroute traffic in case of failures.

**Historical Methods**: Manual monitoring and intervention, which were less efficient and reliable.

#### Theory

**Liveness and Readiness Probes**: Understanding how Kubernetes uses these probes to manage application health and availability.

#### Improvements and Modern Methods

**Custom Probes**: Creating custom health checks for complex applications.

**Integration with Monitoring Tools**: Using tools like Prometheus and Grafana to monitor health check metrics.

#### Interesting Facts

- Kubernetes supports three types of probes: HTTP, TCP, and Command.
- Probes can significantly improve the resilience and uptime of applications.

#### Quiz

1. What is a liveness probe?
2. What is a readiness probe?
3. How does Kubernetes use probes to manage Pods?
4. Explain the purpose of an HTTP probe.
5. What is the difference between liveness and readiness probes?
6. How can you configure a liveness probe?
7. What happens if a liveness probe fails?
8. How can readiness probes affect service availability?
9. What is the default interval for health checks in Kubernetes?
10. How can you monitor probe metrics?

#### Additional Tasks

1. Add liveness and readiness probes to your Nginx deployment.
2. Experiment with different probe configurations (HTTP, TCP, Command).
3. Monitor probe metrics using Prometheus and Grafana.
4. Create custom health checks for a more complex application.


## Final Project
Integrate all the learned topics into a comprehensive project:

1. Repository Setup: Create a private GitHub repository.
2. Terraform Configuration: Write Terraform scripts to deploy a GKE cluster.
3. CI/CD Pipelines: Set up GitHub Actions workflows for Terraform and Docker.
4. Docker Image: Build and push an Nginx Docker image with a static "Hello World" page.
5. Ingress Controller: Deploy an ingress controller using Helm.
6. Kubernetes Deployment: Deploy the Docker image to GKE with appropriate services and ingress.
7. SSL Configuration: Secure the ingress with SSL certificates.
8. Health Checks: Implement and monitor liveness and readiness probes.
