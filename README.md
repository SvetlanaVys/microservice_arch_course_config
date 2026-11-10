# Audio Resource & Song Services Configuration

Centralized configuration repository for the Music Platform microservices architecture.

This repository stores externalized configuration files used by individual microservices through **Spring Cloud Config Server**.

## Architecture

The repository is consumed by the Spring Cloud Config Server, which provides centralized configuration management for the following services:

- API Gateway
- Resource Service
- Song Service
- Resource Processor

## Repository Structure

```text
music-platform-config/
├── application.yml
├── api-gateway.yml
├── eureka-server.yml
├── resource-service.yml
├── song-service.yml
└── resource-processor.yml
```

## Configuration Naming Convention

Spring Cloud Config uses the application name to locate the corresponding configuration file.

| File | Application |
|---|---|
| `application.yml` | Shared configuration |
| `api-gateway.yml` | API Gateway |
| `eureka-server..yml` | Eureka Server |
| `resource-service.yml` | Resource Service |
| `song-service.yml` | Song Service |
| `resource-processor.yml` | Resource Processor |

Environment-specific configurations can be added using Spring profiles.

For example:

- `resource-service-dev.yml`
- `resource-service-prod.yml`

## Configuration Management

1. Update the required configuration file.
2. Commit and push the changes to this repository.
3. Spring Cloud Config Server retrieves the updated configuration.
4. Client services can refresh their configuration at runtime when refresh is supported and triggered.

## Security

- Never commit passwords, API keys, tokens, or other sensitive credentials.
- Use environment variables or a dedicated secrets management solution for sensitive values.
- Restrict repository access according to the deployment environment.
