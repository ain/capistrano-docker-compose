# capistrano-docker-compose

__MOVED__. `capistrano-docker-compose` is now maintained by Interactive Pioneers at https://github.com/interactive-pioneers/capistrano-docker-compose.

capistrano-docker-compose adds Docker containers to Capistrano code deployments making it possible to deploy server stack alongside application.

## Features

As per environment's Docker Compose descriptor:

- Docker image update
- Docker container recreate
- Application cache control upon deployment

## Setup

1. Create Docker Compose descriptors for each environment leaving `docker-compose.yml` as default for development environment, e.g.:
  - `docker-compose.yml`
  - `docker-compose-staging.yml`
  - `docker-compose-production.yml`
2. Set `MASTER_CONTAINER` environment variable for container that will receive maintenance commands on deployment, e.g.:

  ```
  web:
    environment:
      - MASTER_CONTAINER=true
  ```
2. Configure `deploy.rb` with options:

  ```ruby
  # Use with private registry. Not required for public images on Docker Hub.
  :set :docker_registry_server, '<server>'
  :set :docker_registry_username, '<username>'
  :set :docker_registry_password, '<password>'

  # Cache clearing command within MASTER_CONTAINER
  :set :docker_cache_clear, '<command>'
  ```

## Requirements

- Capistrano 3.4+
- Docker Engine 1.11+
- Docker Compose 1.7+

## Licence

Copyright © 2016 Ain Tohvri. Licenced under [GPLv3](LICENSE).
