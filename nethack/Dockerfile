# DESCRIPTION: Run nethack in a container
# AUTHOR: Craig Butcher <hello@craigbutcher.net>
#
# COMMENTS:
#   This file describes how to download and install nethack in a
#   container with all dependencies installed.
#
# TESTED: Alpine latest image
#
# USAGE: Build
#   # Download nethack Dockerfile
#   $ wget https://github.com/craigbutcher/dockerfiles/raw/main/nbsdgames/dockerfile
#
#   # Build nethack image
#   $ docker build -t nethack .
#
#   # Run the nethack image
#   $ docker run -it nethack

FROM alpine:latest

RUN apk --no-cache add nethack

CMD ["/usr/bin/nethack"]
