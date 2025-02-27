# DESCRIPTION: Run vanilla neovim in a container
# AUTHOR: Craig Butcher <hello@craigbutcher.net>
#
# COMMENTS: 
#   This file describes how to download and install the latest neovim in a 
#   container with all dependencies installed.
#
# TESTED: Alpine latest image
#
# USAGE: Build
#   # Download neovim Dockerfile
#   $ wget https://github.com/craigbutcher/dockerfiles/raw/main/neovim/dockerfile
#
#   # Build neovim image
#   $ docker build -t neovim .
#
#   # Run the neovim image with the directory you wish to edit
#   $ docker run -it neovim -v ~/coding

FROM alpine:latest

ARG USER="neovim"
ARG PASS="neovim"
ARG uid=1000
ARG gid=1000

RUN apk --no-cache add neovim && \
	adduser -D $USER && echo "$USER:$PASS" | chpasswd && \
	mkdir -p /home/$USER && \
	mkdir /mnt/storage && \
	chown neovim:neovim /home/$USER && \
	chown neovim:neovim /mnt/storage

USER neovim

CMD ["/usr/bin/nvim"]
