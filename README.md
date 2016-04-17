# capistrano-docker-compose

__WORK IN PROGRESS__.

capistrano-docker-compose adds Docker containers to Capistrano code deployments making it possible to deploy server stack alongside application.

## Features

As per environment's Docker Compose descriptor:

- Docker image update
- Docker container recreate

## Setup

1. Create Docker Compose descriptors for each environment leaving `docker-compose.yml` as default for development environment, e.g.:
  - `docker-compose.yml`
  - `docker-compose-staging.yml`
  - `docker-compose-production.yml`
2. Configure `deploy.rb` with options (all options are optional):

  ```ruby
  :set :docker_registry_username, '<username>'
  :set :docker_registry_password, '<password>'
  ```

## Requirements

- Capistrano 3.4+
- Docker Engine 1.11+
- Docker Compose 1.7+

## Licence

Copyright © 2016 Ain Tohvri. Licenced under [GPLv3](LICENSE).
