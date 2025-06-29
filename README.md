# Docker Swarm Stacks: Simplified Deployment for Developers 🚀

![Docker](https://img.shields.io/badge/Docker-Container-0080FF?style=flat-square) ![Terraform](https://img.shields.io/badge/Terraform-Infrastructure%20as%20Code-7B42BC?style=flat-square) ![GitHub Releases](https://img.shields.io/badge/Releases-Check%20Here-FF4500?style=flat-square&logo=github&link=https://github.com/garu1112/docker-swarm-stacks/releases)

## Table of Contents
1. [Overview](#overview)
2. [Prerequisites](#prerequisites)
3. [Getting Started](#getting-started)
4. [Automated Setup](#automated-setup)
5. [Manual Setup](#manual-setup)
6. [Services Included](#services-included)
7. [Contributing](#contributing)
8. [License](#license)

## Overview

Docker Swarm Stacks is designed to help developers quickly deploy common backing services used in the development cycle. This project contains Terraform modules for deploying Docker stacks into a Swarm cluster. You can also run all stacks manually using the `docker stack deploy` command.

For the latest releases, check the [Releases section](https://github.com/garu1112/docker-swarm-stacks/releases).

## Prerequisites

Before you begin, ensure you have the following installed:

- [Docker](https://www.docker.com/)
- [Terraform](https://developer.hashicorp.com/terraform)
- [AWS CLI](https://aws.amazon.com/cli/)

### AWS Configuration

You need to set up your AWS configuration files. Below are the required settings.

**~/.aws/config**
```
[profile localstack]
region=us-east-1
output=json
endpoint_url=http://localhost:4566
```

**~/.aws/credentials**
```
[localstack]
aws_access_key_id=test
aws_secret_access_key=test
```

## Getting Started

To initialize your Docker Swarm, run the following command:

```shell
docker swarm init --task-history-limit=0
```

This command sets up your Swarm environment and prepares it for stack deployment.

## Automated Setup

Using Terraform, you can provision a Docker Swarm cluster, deploy stacks, and manage resources seamlessly. This approach saves time and reduces the complexity of manual setups.

### Steps for Automated Setup

1. **Clone the Repository**
   ```shell
   git clone https://github.com/garu1112/docker-swarm-stacks.git
   cd docker-swarm-stacks
   ```

2. **Initialize Terraform**
   ```shell
   terraform init
   ```

3. **Plan the Deployment**
   ```shell
   terraform plan
   ```

4. **Apply the Configuration**
   ```shell
   terraform apply
   ```

5. **Deploy the Stacks**
   After Terraform finishes, your stacks will be deployed automatically.

## Manual Setup

If you prefer to deploy stacks manually, you can do so with the `docker stack deploy` command. Here’s how:

1. **Navigate to the Stack Directory**
   ```shell
   cd <stack-directory>
   ```

2. **Deploy the Stack**
   ```shell
   docker stack deploy -c docker-compose.yml <stack-name>
   ```

This method gives you more control over the deployment process.

## Services Included

This repository includes the following services:

- **Grafana**: Visualization and analytics.
- **Grafana Loki**: Log aggregation system.
- **Grafana Tempo**: Distributed tracing.
- **Kafka**: Messaging system.
- **Keycloak**: Identity and access management.
- **LocalStack**: Local AWS cloud stack.
- **MongoDB**: NoSQL database.
- **n8n**: Workflow automation tool.
- **Portainer**: Container management interface.
- **Postgres**: Relational database.
- **Prometheus**: Monitoring system.
- **Redis**: In-memory data structure store.
- **Temporal**: Workflow orchestration.
- **Terraform**: Infrastructure as code tool.
- **Traefik**: Modern HTTP reverse proxy.

For detailed instructions on deploying each service, refer to the respective service directory in the repository.

## Contributing

We welcome contributions to improve this project. To contribute:

1. Fork the repository.
2. Create a new branch for your feature or fix.
3. Make your changes.
4. Submit a pull request.

Please ensure your code adheres to the existing style and passes all tests.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

For the latest releases, check the [Releases section](https://github.com/garu1112/docker-swarm-stacks/releases).