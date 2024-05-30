# Deploying Kubernetes on GCP with CI/CD
By the end of this learning path, participants will have hands-on experience with modern DevOps practices, including version control, infrastructure as code, CI/CD pipelines, containerization, and Kubernetes orchestration.

<br><br>

## Topic 1: Version Control with GitHub

<br>

#### Explanation

**Why it's needed**: Version control systems like GitHub are essential for managing changes to code, enabling collaboration, and maintaining a history of project changes.

**Historical Methods**: Earlier methods included manual versioning and centralized systems like SVN, which had limitations in collaboration and version control.

<br>

#### Theory

##### Key Git Concepts

| Concept                         | Kurzgesagt                                                                                                              | Definition                                                                                                                                                                                                                                              | Function                                                                                                                                                                                                                                                                                          |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **1. Repositories**             | Central storage for project code and history.                                                                           | A repository (or "repo") is a storage location for software projects. It contains all the files, directories, and the history of changes (commits) for a project.                                                                                       | Repositories are used to organize and manage the codebase, allowing multiple developers to collaborate on the same project. Each repository can be cloned to a local machine, where changes can be made and then pushed back to the remote repository.                                            |
| **2. Commits**                  | Snapshots of changes with metadata for tracking progress.                                                               | A commit is a snapshot of changes made to the files in a repository. Each commit records the state of the project at a specific point in time.                                                                                                          | Commits are used to track changes in a repository. Each commit has a unique identifier (hash) and includes metadata such as the author, timestamp, and a commit message describing the changes. This makes it easy to review the history of changes and revert to previous states if necessary.   |
| **3. Branches**                 | Parallel versions of the codebase for isolated development.                                                             | A branch is a parallel version of a repository. It diverges from the main codebase (often called "main" or "master") to allow for independent development without affecting the stable codebase.                                                        | Branches are used to develop features, fix bugs, or experiment with new ideas. Once changes on a branch are tested and verified, they can be merged back into the main codebase. This allows for isolated development and easier management of different versions of the project.                 |
| **4. Merges**                   | Combining changes from different branches into one.                                                                     | A merge is the process of integrating changes from one branch into another. This often involves combining the contents of different branches and resolving any conflicts that arise.                                                                    | Merges are used to consolidate changes from different branches, ensuring that all updates are incorporated into the main codebase. This is a critical step in collaborative development, allowing multiple branches to converge into a single, unified project.                                   |
| **5. Pull Requests**            | Mechanism for submitting, reviewing, and merging contributions.                                                         | A pull request (PR) is a method for submitting contributions to a project. It allows developers to notify others about changes they've made in a branch and request that these changes be reviewed and merged into the main branch.                     | Pull requests are used to facilitate code review and collaboration. They provide a platform for discussing changes, reviewing code, and ensuring that contributions meet the project's standards before being merged. This process helps maintain code quality and encourages team collaboration. |
| **6. Private Repositories**     | Restricted access, ideal for confidential or internal projects.                                                         | Private repositories are repositories that are only accessible to the repository owner and specific collaborators who are granted access. They are not visible to the general public.                                                                   | Used for proprietary projects, internal development, or any work that should not be publicly accessible. Only authorized users can view, clone, and contribute to the repository.                                                                                                                 |
| **7. Public Repositories**      | Open access, suitable for open-source and community collaboration.                                                      | Public repositories are repositories that anyone can access. They are visible to everyone, and anyone can clone or download the code.                                                                                                                   | Ideal for open-source projects, sharing knowledge, and collaboration with a wider community. Contributions can be made by anyone through pull requests, making it a key tool for open-source development.                                                                                         |
| **8. Collaboration Tools**      | Features like issues, pull requests, project boards, code review, and wikis to enhance teamwork and project management. | Collaboration tools in GitHub are features and integrations that facilitate teamwork and project management. These tools help coordinate efforts, manage tasks, and communicate effectively within a team.                                              | **Issues**: Track tasks, enhancements, and bugs for your projects.                                                                                                                                                                                                                                  |
|                                 |                                                                                                                         |                                                                                                                                                                                                                                                         | **Pull Requests**: Review and discuss proposed changes before merging them.                                                                                                                                                                                                                         |
|                                 |                                                                                                                         |                                                                                                                                                                                                                                                         | **Project Boards**: Organize and prioritize work using Kanban-style boards.                                                                                                                                                                                                                         |
|                                 |                                                                                                                         |                                                                                                                                                                                                                                                         | **Code Review**: Review changes and leave feedback on pull requests.                                                                                                                                                                                                                                |
|                                 |                                                                                                                         |                                                                                                                                                                                                                                                         | Wikis: Document your projects and share knowledge within the team.                                                                                                                                                                                                                              |
| **9. GitHub Actions for CI/CD** | Automates building, testing, and deploying applications through customizable workflows triggered by repository events.  | GitHub Actions is a CI/CD (Continuous Integration/Continuous Deployment) platform that automates the build, test, and deployment processes of your applications. It allows you to create workflows that are triggered by events within your repository. | CI (Continuous Integration): Automatically build and test your code every time a change is pushed to the repository, ensuring that new commits do not break the project.                                                                                                                        |
|                                 |                                                                                                                         |                                                                                                                                                                                                                                                         | CD (Continuous Deployment): Automate the deployment of your application to various environments (e.g., staging, production) after passing all tests and checks.                                                                                                                                 |
|                                 |                                                                                                                         |                                                                                                                                                                                                                                                         | Workflows: Defined using YAML files, these workflows specify the actions to be performed in response to specific events, such as pushes, pull requests, or scheduled intervals.                                                                                                                 |
|                                 |                                                                                                                         |                                                                                                                                                                                                                                                         | Runners: Servers that execute the workflows. GitHub provides hosted runners, but you can also use self-hosted runners for more control over the environment.                                                                                                                                    |

<br>

#### Improvements and Modern Methods

**Better Collaboration**: Use of pull requests and code reviews.

- **Pull Requests (PRs)**: A pull request is a method for proposing changes to a repository. It allows developers to request that someone review and merge their changes into another branch, typically the main branch.
    - *Example*:
        - Developer Alice creates a new branch `feature-xyz` from the main branch.
        - She makes her changes and pushes `feature-xyz` to the remote repository.
        - Alice then opens a pull request from `feature-xyz` to `main`, adding a detailed description of the changes.
        - Reviewers can comment on specific lines, suggest changes, and ultimately approve the PR for merging.
- **Code Reviews**: The process of systematically examining code changes by other developers before merging them.
    - *Example*:
        - Bob reviews Alice's pull request. He notices a potential issue in the logic.
        - Bob leaves a comment on the specific line of code and suggests an alternative approach.
        - Alice makes the recommended changes and updates the PR.
        - After a few iterations, Bob approves the PR, and it gets merged into the `main` branch.

**Automation**: Integrating CI/CD pipelines with GitHub Actions.

- **CI/CD**: Continuous Integration (CI) involves automatically building and testing code changes as they are made. Continuous Deployment (CD) extends this by automatically deploying the code to production once it passes all tests.
- **GitHub Actions**: A CI/CD platform provided by GitHub that allows you to automate workflows directly in your GitHub repository using YAML files.
    - *Example*:
        - Workflow Configuration: Create a `.github/workflows/ci.yml` file.
        - The workflow below runs every time there is a push or pull request. It checks out the code, sets up Node.js, installs dependencies, and runs tests.

```yaml
name: CI
on: [push, pull_request]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - name: Set up Node.js
      uses: actions/setup-node@v2
      with:
        node-version: '14'
    - run: npm install
    - run: npm test
```

**Security**: Using branch protection and security policies.

- **Branch Protection**: GitHub provides branch protection rules to enforce specific workflows and quality checks before merging.
    - *Example*:
        - Require pull requests to be reviewed before merging.
        - Enforce status checks to pass before merging.
        - Restrict who can push to the branch.
- **Security Policies**: These include setting up security policies, using Dependabot for automated dependency updates, and enforcing code scanning to identify vulnerabilities.
    - *Example*:
        - Create a `SECURITY.md` file to outline the security policies and procedures.
        - Enable Dependabot to automatically open pull requests for outdated or vulnerable dependencies.
        - Configure code scanning tools like CodeQL to scan the repository for potential security issues.

<br>

#### Interesting Facts

- Git was created by Linus Torvalds in 2005.
- GitHub hosts over 100 million repositories as of 2024.
- Code reviews have been shown to reduce the number of defects in software significantly.
- Linus Torvalds, creator of Git, emphasized the importance of code reviews in maintaining the quality of the Linux kernel.
- CI/CD automation can reduce the average time to resolve issues by up to 20%.
- GitHub Actions allows you to create custom actions, enabling reusable workflows across multiple projects.
- GitHub Dependabot can automatically create PRs to update dependencies, helping maintain security without manual intervention.
- Branch protection rules can be customized to fit the specific needs of a project, providing flexibility and control over the development workflow.

<br>

#### Quiz

1. **What is a Git repository?**
    - *A Git repository is a storage location for a software project, containing all files, directories, and the entire history of changes. It allows multiple developers to collaborate by tracking changes, merging updates, and maintaining versions.*<br><br>

2. **Explain the difference between git pull and git fetch.**
    - *`git fetch` downloads updates from the remote repository to the local repository without merging them into the working directory. `git pull` fetches the updates and immediately merges them into the local branch, updating the working directory.*<br><br>

3. **What is a pull request?**
    - *A pull request is a method for submitting changes to a repository. It allows developers to notify others about the changes they've made, request reviews, and discuss potential modifications before merging the changes into the main branch.*<br><br>

4. **How do you revert a commit in Git?**
    - *To revert a commit, use the `git revert <commit-hash>` command, which creates a new commit that undoes the changes made by the specified commit, preserving the history.*<br><br>

5. **What are GitHub Actions used for?**
    - *GitHub Actions are used to automate workflows, such as continuous integration (CI) and continuous deployment (CD). They allow you to build, test, and deploy your code based on events like pushes, pull requests, and scheduled tasks.*<br><br>

6. **Define branching in Git.**
    - *Branching in Git involves creating separate lines of development within a repository. Branches allow you to work on features, fixes, or experiments in isolation from the main codebase, and later merge them back when ready.*<br><br>

7. **What is the purpose of a .gitignore file?**
    - *A `.gitignore` file specifies which files and directories Git should ignore and not track. This is useful for excluding files that are generated during development, such as build artifacts, temporary files, and sensitive information.*<br><br>

8. **How can you protect a branch in GitHub?**
    - *You can protect a branch in GitHub by enabling branch protection rules, which can include requiring pull requests for changes, enforcing status checks, requiring reviews before merging, and restricting who can push to the branch.*<br><br>

9. **What command is used to stage changes in Git?**
    - *The command `git add <file>` is used to stage changes, marking them for inclusion in the next commit. You can stage all changes with `git add .`.*<br><br>

10. **Explain the use of forks in GitHub.**
    - *Forks are copies of repositories that allow developers to freely experiment with changes without affecting the original project. Forks enable users to work on their own version of a project, contribute back through pull requests, and explore modifications independently.*<br><br>

<br>

#### Additional Tasks

1. [Create a new GitHub repository.](https://github.com/kichukowa/WEB)
2. [Make and commit changes to a README file.](https://github.com/kichukowa/github-docs)
3. Create branches and practice merging.
4. Set up branch protection rules.
5. [Explore GitHub Actions by creating a simple workflow.](https://github.com/kichukowa/tf-review-plan)

<br><br>

## Topic 2: Infrastructure as Code with Terraform

<br>

#### Explanation

**Why it's needed**: IaC allows for the automation and consistency of infrastructure deployment.

**Historical Methods**: Manual configuration and deployment using scripts and CLI commands, which were error-prone and not easily replicable.

<br>

#### Theory

**Terraform Basics**: Providers, resources, variables, state management, and modules.

**GKE Deployment**: Setting up GCP provider, creating a GKE cluster, and managing state.

<br>

#### Improvements and Modern Methods

**Reusable Modules**: Creating reusable and shareable modules for standard configurations.

**State Management**: Using remote state backends for collaboration.

**Automation**: Integrating Terraform with CI/CD pipelines for continuous deployment.

<br>

#### Interesting Facts

- Terraform supports multiple cloud providers including AWS, Azure, GCP, and many others.
- The concept of IaC significantly reduces configuration drift and improves consistency.

<br>

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

<br>

#### Additional Tasks

1. Set up a basic Terraform configuration for a GKE cluster.
2. Use variables and outputs in your configuration.
3. Explore and use a remote backend for state management.
4. Create a reusable Terraform module.

<br><br>

## Topic 3: Continuous Integration/Continuous Deployment (CI/CD) with GitHub Actions

<br>

#### Explanation

**Why it's needed**: CI/CD automates the testing and deployment process, ensuring code is always in a deployable state.

**Historical Methods**: Manual builds and deployments, leading to frequent errors and inconsistent environments.

<br>

#### Theory

**CI/CD Basics**: Understanding the principles of continuous integration, delivery, and deployment.

**GitHub Actions**: YAML syntax, jobs, steps, and runners. Creating workflows for CI/CD.

<br>

#### Improvements and Modern Methods

**Parallel Jobs**: Running jobs in parallel to speed up the CI/CD process.

**Artifact Management**: Storing and reusing build artifacts.

**Security**: Managing secrets and permissions in workflows.

<br>

#### Interesting Facts

- CI/CD pipelines significantly reduce the time to market for new features.
- GitHub Actions allows you to run workflows directly in the cloud without needing your own CI server.

<br>

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

<br>

#### Additional Tasks

1. Create a simple CI workflow to build and test a project.
2. Set up a CD workflow to deploy an application.
3. Use GitHub secrets to manage sensitive information.
4. Experiment with matrix builds to test across different environments.

<br><br>

## Topic 4: Containerization with Docker

<br>

#### Explanation

**Why it's needed**: Containers ensure consistency across development and production environments by packaging applications and their dependencies.

**Historical Methods**: Applications were run directly on the host OS, leading to dependency and environment issues.

<br>

#### Theory

**Docker Basics**: Images, containers, Dockerfile, Docker Hub.

**Creating a Dockerfile**: Defining a Dockerfile to build an Nginx server with a static page.

<br>

#### Improvements and Modern Methods

**Multi-Stage Builds**: Reducing image size and improving build efficiency.

**Docker Compose**: Managing multi-container applications.

**Security**: Best practices for securing Docker images.

<br>

#### Interesting Facts

- Docker was introduced in 2013 and has revolutionized the way applications are deployed.
- As of 2024, Docker Hub hosts millions of container images.

<br>

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

<br>

#### Additional Tasks

1. Write a Dockerfile for a simple application.
2. Build and push a Docker image to Docker Hub.
3. Use Docker Compose to manage a multi-container application.
4. Implement best practices for Docker image security.

<br><br>

## Topic 5: Kubernetes Basics and GKE

<br>

#### Explanation

**Why it's needed**: Kubernetes automates the deployment, scaling, and management of containerized applications.

**Historical Methods**: Manual container orchestration or using simpler tools like Docker Swarm.

<br>

#### Theory

**Kubernetes Concepts**: Pods, nodes, clusters, deployments, services, and ingress.

**GKE**: Google Kubernetes Engine simplifies Kubernetes deployment and management in the cloud.

<br>

#### Improvements and Modern Methods

**Autoscaling**: Automatically adjusting the number of pods based on load.

**Stateful Applications**: Managing stateful applications using StatefulSets.

**Security**: Implementing RBAC and network policies.

<br>

#### Interesting Facts

- Kubernetes was originally developed by Google and released as open-source in 2014.
- GKE is a managed Kubernetes service that handles cluster management tasks like upgrades and scaling.

<br>

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

<br>

#### Additional Tasks

1. Deploy a simple application to a local Kubernetes cluster using Minikube.
2. Create and manage Kubernetes resources like Pods, Deployments, and Services.
3. Explore GKE and deploy a Kubernetes application to it.
4. Implement autoscaling for your application.

<br><br>

## Topic 6: Networking and Ingress in Kubernetes

<br>

#### Explanation

**Why it's needed**: Networking in Kubernetes manages communication within the cluster and exposes applications to external traffic.

**Historical Methods**: Manual configuration of networking routes and load balancers.

<br>

#### Theory

**Kubernetes Networking**: Services, Ingress controllers, and network policies.

**Ingress Controllers**: Managing external access to services in a Kubernetes cluster.

<br>

#### Improvements and Modern Methods

**Service Mesh**: Using tools like Istio for advanced networking features.

**Network Policies**: Implementing fine-grained control over network traffic.

<br>

#### Interesting Facts

- Kubernetes uses a flat network model, where all Pods can communicate with each other by default.
- Ingress controllers can manage SSL termination and load balancing.

<br>

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

<br>

#### Additional Tasks

1. Deploy an Ingress controller using Helm.
2. Configure an Ingress resource to route traffic to your application.
3. Implement SSL for your Ingress resource.
4. Explore and implement network policies in your cluster.

<br><br>

## Topic 7: Health Checks in Kubernetes

<br>

#### Explanation

**Why it's needed**: Health checks ensure that applications are running correctly and can automatically restart or reroute traffic in case of failures.

**Historical Methods**: Manual monitoring and intervention, which were less efficient and reliable.

<br>

#### Theory

**Liveness and Readiness Probes**: Understanding how Kubernetes uses these probes to manage application health and availability.

<br>

#### Improvements and Modern Methods

**Custom Probes**: Creating custom health checks for complex applications.

**Integration with Monitoring Tools**: Using tools like Prometheus and Grafana to monitor health check metrics.

<br>

#### Interesting Facts

- Kubernetes supports three types of probes: HTTP, TCP, and Command.
- Probes can significantly improve the resilience and uptime of applications.

<br>

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

<br>

#### Additional Tasks

1. Add liveness and readiness probes to your Nginx deployment.
2. Experiment with different probe configurations (HTTP, TCP, Command).
3. Monitor probe metrics using Prometheus and Grafana.
4. Create custom health checks for a more complex application.

<br><br>

## Final Project
Integrate all the learned topics into a comprehensive project:

<br>

##### STEP 1. Setup a New Private Project in GitHub and Terraform Configuration

1. **Create a New GitHub Repository**:
    - Go to GitHub and create a new repository.
        - [New Repo](https://github.com/kichukowa/kubernetes-deploy)
    - Make sure to set it as private.
    <br><br>

2. **Initialize Terraform Configuration**:
    - On your local machine, create a directory for your project.
    - Inside this directory, create another directory called `terraform`.
    - Initialize a new Git repository in your project directory.
    <br><br>

3. **Terraform Files**:
    - **Provider Configuration**: Create a `provider.tf` to configure the Google Cloud provider.
    - **Variables**: Create a `variables.tf` to define variables like project ID, region, and cluster name.
    - **Main Configuration**: Create a `main.tf` to define the resources, including the GKE cluster and node pools.
    - **Outputs**: Create an `outputs.tf` to output the necessary information, such as cluster endpoint and credentials.

4. **GitHub Actions CI/CD Job for Terraform**:
    - Create a directory `.github/workflows` and add a YAML file (e.g., `infrastructure.yml`).
    - This file will define a workflow to initialize Terraform, plan, and apply the configuration whenever changes are pushed to the `terraform` directory.
    <br><br>

##### STEP 2. Terraform Configuration: Write Terraform scripts to deploy a GKE cluster.

1. 

2. 

3. 

##### STEP 3. CI/CD Pipelines: Set up GitHub Actions workflows for Terraform and Docker.

1. 

2. 

3. 

##### STEP 4. Docker Image: Build and push an Nginx Docker image with a static "Hello World" page.

1. 

2. 

3. 

##### STEP 5. Ingress Controller: Deploy an ingress controller using Helm.

1. 

2. 

3. 

##### STEP 6. Kubernetes Deployment: Deploy the Docker image to GKE with appropriate services and ingress.

1. 

2. 

3. 

##### STEP 7. SSL Configuration: Secure the ingress with SSL certificates.

1. 

2. 

3. 

##### STEP 8. Health Checks: Implement and monitor liveness and readiness probes.

1. 

2. 

3. 
