# Docker Compose

- [Source](https://docs.docker.com/compose/overview/): Taken from official docker documentation. 

## Definition
- Tool to define and run multi-container Docker application
- `.yml`/ `.yaml` file is used to configure the application services. Then with a single command we can create and start all the services from our configuration.
- Works in all environments: production, staging, development, testing as well as CI workflows

## 3 step process in using compose
1. Define app's environment with a `Dockerfile` so that it can be reproduced annywhere.
2. Define the services that make up your app in `docker-compose.yml` so they can be run together in an isolated environment.
3. Run `docker-compose up` and Compose starts and runs your entire app.
