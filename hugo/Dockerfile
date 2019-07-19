#  docker build -t sigje/hugo .
#  docker run --rm -v `pwd`:/pwd/ -p 1313:1313/tcp -it sigje/hugo
FROM alpine:latest
# Make sure that HUGO_VERSION is set to a version of HUGO supported by whatever theme is in use
ENV HUGO_VERSION 0.55.6
LABEL maintainer iennae@gmail.com

# Installing a few non-required packages for development purposes
RUN apk --no-cache add ca-certificates curl tar bash vim git tree

RUN curl -L https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_${HUGO_VERSION}_Linux-64bit.tar.gz | tar -zOxf - hugo > /usr/bin/hugo && chmod +x /usr/bin/hugo

# WORKDIR is set up so that I can host a copy of this Dockerfile inside the 
# source code for the static website project.
WORKDIR /pwd/
EXPOSE 1313

# This starts up hugo so I can connect from a browser on my local system
CMD hugo server --bind="0.0.0.0" 
