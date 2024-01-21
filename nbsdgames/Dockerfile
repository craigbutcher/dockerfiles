# DESCRIPTION: Run nbsdgames in a container
# AUTHOR: Craig Butcher <hello@craigbutcher.net>
#
# COMMENTS:
#   This file describes how to download and install nbsdgames in a
#   container with all dependencies installed.
#
# TESTED: Alpine latest image
#
# USAGE: Build
#   # Download nbsdgames Dockerfile
#   $ wget https://github.com/craigbutcher/dockerfiles/raw/main/nbsdgames/dockerfile
#
#   # Build nbsdgames image
#   $ docker build -t nbsdgames .
#
#   # Run the nbsdgames image
#   $ docker run -it nbsdgames

FROM alpine

RUN apk --no-cache add \
        build-base git ncurses ncurses-dev && \
        git clone https://github.com/abakh/nbsdgames.git && \
        cd nbsdgames && make && make install && cd .. && rm -rf nbsdgames && \
        apk del build-base git ncurses-dev

CMD ["/usr/bin/nbsdgames"]
