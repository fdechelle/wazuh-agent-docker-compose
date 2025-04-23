FROM ubuntu:noble AS base
# install git and python
RUN apt-get update -qq; apt-get install -y git python3 python3-pip ; apt-get clean

# install IDMEFv2 python library
RUN pip install --break-system-packages --extra-index-url https://test.pypi.org/simple/ idmefv2

# install IDMEFv2 connectors
WORKDIR /
ARG IDMEFV2_CONNECTORS_GIT=./files/base/idmefv2-connectors
COPY ${IDMEFV2_CONNECTORS_GIT} /idmefv2-connectors/
WORKDIR /idmefv2-connectors
RUN pip install --break-system-packages .
