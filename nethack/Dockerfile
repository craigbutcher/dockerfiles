# DESCRIPTION: Run nethack in a container
# AUTHOR: Craig Butcher <hello@craigbutcher.net>
#
# COMMENTS:
#   This file describes how to download and install nethack in a
#   container with all dependencies installed.
#
#   Tested on Alpine latest image
#
# USAGE: Build
#   # Download nethack Dockerfile
#   wget https://github.com/craigbutcher/dockerfiles/raw/main/nbsdgames/dockerfile
#
#   # Build nbsdgames image
#   docker build -t nbsdgames .
#
#   # Run the nbsdgames image
#   docker run -it nbsdgames

# Base docker image

# Base docker image
FROM alpine:latest
# LABEL:

# Run up
RUN apk --no-cache add nethack

CMD ["/usr/bin/nethack"]
