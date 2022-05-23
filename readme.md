Spring Microservice Architecture Sample Project

**Services:**
- Gateway
- Service Registry
- Employee-service
- Department-service
- Hystrix-Dashboard
  Hystrix service is available at http://localhost:9090/hystrix/monitor, add the stream url as gateway:8888/actuator/hystrix.stream
  to get the metrics on dashboard.

Details about services

- Explore the Employee service and Department service to understand about the APIs
- Services' has its own database image/instance.
- This project is to be deployed on docker, each project has Dockerfile. See Deployment steps to know in detail.
- It has maven as build tool.

### Deployment steps*

- For all services/projects it has its own Dockerfile to build a docker image.
- To build a docker image 
  1. Do maven clean
  2. Do maven install to build a jar (skip test if required)
  3. From project parent directory execute docker command to build the image as "docker build -t <image name> .", it will take current project's Dockerfile and will create an image.
  4. Once you create images for all the services, you should see them in docker.
  5. After that docker compose comes in a picture, the docker-compose.yml is located in service registry.**
  6. Run "docker compose up" command to deploy all the images in single/grouped container in same network.

*read about basic docker(docker compose) concepts to understand given below steps.

**If we have single service we can deploy/run with separate container, as we have multiple services and which should be in single network, we will use docker compose.
