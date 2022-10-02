# DESCRIPTION: Run elinks in a container
# AUTHOR: Craig Butcher <hello@craigbutcher.net>
#
# COMMENTS: 
#   This file describes how to download and install elinks in a 
#   container with all dependencies installed.
#
#   Tested on Alpine edge image
#
# USAGE: Build
#   # Download elinks Dockerfile
#   wget https://github.com/craigbutcher/dockerfiles/raw/main/elinks/dockerfile
#
#   # Build wrp image
#   docker build -t elinks .
#
#   # Run the wrp image either via command or docker-compose
#   docker run -it -p 80:80 -p 443:443 elinks
#   or   
#   docker compose up

# Base docker image

FROM alpine:latest

RUN apk --no-cache add \
        wget ncurses-terminfo-base && \
        wget https://github.com/rkd77/elinks/releases/download/v0.15.1/elinks-0.15.1-armhf-bin.tar.xz && \
        tar xvf elinks-0.15.1-armhf-bin.tar.xz && \
        cd elinks-0.15.1-armhf-bin && \
        mv elinks /usr/local/bin/ && \
        rm -rf elinks*

CMD ["/usr/local/bin/elinks"]
