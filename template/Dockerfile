# DESCRIPTION: Run app in a container
# AUTHOR: Craig Butcher <hello@craigbutcher.net>
#
# COMMENTS:
#   This file describes how to download and install the latest app in a
#   container with all dependencies installed.
#
# TESTED: Alpine latest image
#
# USAGE: Build
#   # Download app Dockerfile
#   $ wget https://github.com/craigbutcher/dockerfiles/raw/main/app/dockerfile
#
#   # Build app image
#   $ docker build -t app .
#
#   # Run the app image
#   $ docker run -it app

FROM alpine:latest

# Do whatever is required to install the app
RUN apk --no-cache add

CMD ["/usr/local/bin/app"]
