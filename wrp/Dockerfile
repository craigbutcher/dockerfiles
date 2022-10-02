# DESCRIPTION: Run WRP in a container
# AUTHOR: Craig Butcher <hello@craigbutcher.net>
#
# COMMENTS: 
#	This file describes how to build wrp in a container with all
#	dependencies installed.
#
#   Tested on Alpine edge image
#
# USAGE: Build
#	# Download wrp Dockerfile
#	wget https://github.com/craigbutcher/dockerfiles/raw/main/wrp/dockerfile
#
#	# Build wrp image
#	docker build -t wrp .
#
#   # Run the wrp image either via command or docker-compose
#	docker run -it -p 8080:8080 wrp
#   or
#   docker compose up

FROM alpine:edge

RUN apk update && apk add chromium wget && \
    wget https://github.com/tenox7/wrp/releases/download/4.5.2/wrp-arm64-linux && \
    chmod +x wrp-arm64-linux

CMD ["/wrp-arm64-linux"]
