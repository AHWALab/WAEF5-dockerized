################################################################################
#            EF5: ENSEMBLE FRAMEWORK FOR FLASH FLOOD FORECASTING
#                          DOCKER IMPLEMENTATION
################################################################################
# Author: Jorge A. Duarte
# Email: jduarte@ou.edu/jorge.duarte@noaa.gov
# Version: 1.0
# Date: Apr. 09, 2023
# ------------------------------------------------------------------------------
# This Dockerfile builds one Docker image:
# - 'ef5-container' image which will compile and host the EF5 installation,
# linked to two distinct shared folders:
#    + ./conf: where the container will look for an EF5 control file
#    + ./data: where the container will look for the required data to run EF5 
#
# These image must be instantiated using docker-compose and ./docker-compose.yml
################################################################################


################################################################################
#                    BUILD ARGUMENTS & ENVIRONMENT VARIABLES
################################################################################
# Use a minimal Alpine Linux base image from Dockerhub for our custom container
# This Linux image is ideal, since it weights only 5MB!
ARG DOCKER_BASE_OS="alpine:3.17"

################################################################################
#      BUILD A STANDARD ALPINE LINUX IMAGE FOR THE APPLICATION CONTAINER
################################################################################
FROM ${DOCKER_BASE_OS} AS ef5-image
LABEL nssl.wrdd.image.authors="jorge.duarte@noaa.gov"

# Define VOLUMES for Bind Mounts
VOLUME [ "/conf" ]
VOLUME [ "/data" ]
VOLUME [ "/results" ]

# Update the package index
RUN apk update

# Install git, autoconf, automake, and 'build essentials' packages
RUN apk add git
RUN apk add automake
RUN apk add autoconf
RUN apk add build-base

# Install EF5 dependencies
# LibGeoTIFF
RUN apk add libgeotiff-dev


# Set the EF5-DOCKERIZED folder as the working directory
WORKDIR ../

# Clone EF5 from GitHub onto the ef5 folder in the project root
RUN git clone https://github.com/HyDROSLab/EF5.git ./ef5

# Set the ef5 folder as the working directory
WORKDIR ./ef5

# Compile and install EF5
RUN autoreconf --force --install
RUN ./configure
RUN make

# Run ef5
CMD ["/ef5/bin/ef5", "/conf/control.txt"]