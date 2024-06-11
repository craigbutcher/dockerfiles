# DESCRIPTION: Run tetris (via emacs) in a container
# AUTHOR: Craig Butcher <hello@craigbutcher.net>
#
# COMMENTS:
#   This file describes how to download and install tetris in a
#   container with all dependencies installed.
#
# TESTED: Alpine latest image
#
# USAGE: Build
#   # Download tetris Dockerfile
#   wget https://github.com/craigbutcher/dockerfiles/raw/main/tetris/dockerfile
#
#   # Build tetris image
#   docker build -t tetris .
#
#   # Run the tetris image either via command or docker-compose
#   docker run -it tetris

# Base docker image

FROM alpine:latest

RUN apk --no-cache add emacs-nox

CMD ["/usr/bin/emacs", "-f", "tetris"]
