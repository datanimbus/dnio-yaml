# dnio-yaml

This repository holds YAML configuration files for key components. Here's a quick guide:

### 1. cache.yaml

Configures Redis caching service and deployment.

- **Service:** `cache`
  - Namespace: `__namespace__`
  - Type: ClusterIP
  - Ports: 6379

- **Deployment:** Replicas: 1, Image: `redis:5-alpine`, Volume: `/mnt/cache`

### 2. messaging.yaml

Sets up NATS messaging service and deployment.

- **Service:** `messaging`
  - Namespace: `__namespace__`
  - Type: ClusterIP
  - Ports: 4222

- **Deployment:** Replicas: 1, Image: `nats-messaging:0.11.2`, Volume: `/mnt/store`

### 3. configMap.yaml

Configures a Kubernetes ConfigMap with environment-specific settings:

- Logging levels
- MongoDB connection
- Streaming service
- Cache details
- Docker registry
- RBAC session variables

## Usage

1. Clone the repository.
2. Update YAML files with your values (e.g., `__namespace__`, `__FQDN__`, `__db_host__`).
3. Apply configurations using `kubectl apply -f <filename>`.


