# DESCRIPTION: Run elinks in a container
# AUTHOR: Craig Butcher <hello@craigbutcher.net>
#
# COMMENTS: 
#   This file describes how to download and install the latest elinks in a 
#   container with all dependencies installed.
#
# TESTED: Alpine latest image
#
# USAGE: Build
#   # Download elinks Dockerfile
#   $ wget https://github.com/craigbutcher/dockerfiles/raw/main/elinks/dockerfile
#
#   # Build elinks image
#   $ docker build -t elinks .
#
#   # Run the elinks image
#   $ docker run -it elinks

FROM alpine:latest

RUN apk --no-cache add \
        curl jq tar xz && \
        curl -s https://api.github.com/repos/rkd77/elinks/releases/latest | \
        jq -r '.assets[0].browser_download_url' | \
        xargs -I {} sh -c 'file=$(basename {}); curl -L {} -o "$file" && tar -xf "$file"' && \
        dir=$(find . -type d -name "*elinks*") && \
        mv $dir/elinks /usr/local/bin/ && \
        rm -rf elinks* && \
        apk del curl jq xz

CMD ["/usr/local/bin/elinks"]
