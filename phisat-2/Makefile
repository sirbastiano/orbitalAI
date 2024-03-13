# Variables
IMAGE_NAME := orbitalaisimulator
TAG := ubuntu_22.04
DOCKER_USERNAME := sirbastiano94
REPO_NAME := orbitalai

# Default action
all: build run

# Build Docker image
build:
	docker build --platform linux/amd64 -t $(IMAGE_NAME):$(TAG) .


# Push Docker image to Docker Hub
push:
	docker login
	docker tag $(IMAGE_NAME):$(TAG) $(DOCKER_USERNAME)/$(REPO_NAME):$(TAG)
	docker push $(DOCKER_USERNAME)/$(REPO_NAME):$(TAG)


run:
	docker run -it --rm --platform linux/amd64 $(IMAGE_NAME):$(TAG)

# Help
help:
	@echo "Makefile for building and pushing Docker images"
	@echo ""
	@echo "Usage:"
	@echo "  make build        - Build the Docker image"
	@echo "  make tag          - Tag the Docker image"
	@echo "  make push         - Push the Docker image to Docker Hub"
	@echo "  make login        - Login to Docker Hub"
	@echo "  make all          - Execute build, tag, and push"
