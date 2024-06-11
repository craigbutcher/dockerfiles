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
#	docker run -it -p 9000:8080 wrp
#   or
#   docker compose up

FROM alpine:edge

ARG TARGETPLATFORM

RUN apk --no-cache add chromium curl jq && \
    case "$TARGETPLATFORM" in \
        'linux/amd64') BIN='wrp-amd64-linux' ;; \
        'linux/arm64') BIN='wrp-arm64-linux' ;; \
        'linux/arm/v7') BIN='wrp-arm-linux' ;; \
        *) echo "Unsupported platform: $TARGETPLATFORM"; exit 1 ;; \
    esac && \
    curl -s https://api.github.com/repos/tenox7/wrp/releases/latest | \
    jq -r --arg bin "$BIN" '.assets[] | select(.name == $bin).browser_download_url' | \
    xargs -I {} sh -c 'file=$(basename {}); curl -L {} -o "$file" && chmod +x "$file"' && \
    apk del curl jq

CMD ["/wrp-arm64-linux"]
