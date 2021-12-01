# dockerized-production-flask-api
A basic flask API scaffold for development and production environments using Traefik, Flask, Gunicorn with Let's Encrypt Capabilities.

## How to Use
### Production Environment
1. Run the following command from the root folder:
```
docker-compose -f docker-compose.prod.yml up -d --build
```
Note that in the production build we use a Docker multi-stage build to reduce the final image size. Essentially, builder is a temporary image that's used for building the Python wheels. The wheels are then copied over to the final production image and the builder image is discarded.
It is also important to note that we create a non-root user in this dockerfile.

### Development Environment
1. Run the following command from the root folder:
```
docker-compose up -d --build
```
