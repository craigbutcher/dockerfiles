# DESCRIPTION: Run neovim with kickstart.nvim in a container
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
#   $ wget https://github.com/craigbutcher/dockerfiles/raw/main/neovim-kickstart/dockerfile
#
#   # Build neovim image
#   $ docker build -t neovim-kickstart .
#
#   # Run the neovim image with the directory you wish to edit
#   $ docker run -it neovim-kickstart -v ~/coding

FROM alpine:latest

ARG USER="neovim"
ARG PASS="neovim"
ARG uid=1000
ARG gid=1000

RUN apk --no-cache add \
	gcc git make musl-dev neovim ripgrep unzip && \
	adduser -D $USER && echo "$USER:$PASS" | chpasswd && \
	mkdir -p /home/$USER && \
	mkdir /mnt/storage && \
	chown neovim:neovim /home/$USER && \
	chown neovim:neovim /mnt/storage

USER neovim

RUN cd /home/neovim && mkdir -p .config/ && \
	git clone https://github.com/nvim-lua/kickstart.nvim.git "${XDG_CONFIG_HOME:-$HOME/.config}"/nvim

CMD ["/usr/bin/nvim"]
