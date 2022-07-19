# UnrealEngineMultiUserServer_Docker
This repository aim to describe a docker image for hosting a Unreal Engine Multi User Server.

FROM_IMAGE="$(cat to build.properties | grep -m 1 FROM_IMAGE | cut -d '=' -f2)"

IMAGE_TAG="$(cat to build.properties | grep -m 1 IMAGE_TAG | cut -d '=' -f2)"

IMAGE_NAME="$(cat to build.properties | grep -m 1 IMAGE_NAME | cut -d '=' -f2)"

UNREAL_VERSION="$(cat to build.properties | grep -m 1 UNREAL_VERSION | cut -d '=' -f2)"

kaniko/executor
--context "Path to repo docker"
--dockerfile "Path to dockerfile"
--build-arg FROM_IMAGE=$FROM_IMAGE
--build-arg IMAGE_TAG=$IMAGE_TAG
--build-arg IMAGE_NAME=$IMAGE_NAME
--build-arg UNREAL_VERSION=$UNREAL_VERSION
--destination dockerhub/$IMAGE_NAME:IMAGE_TAG