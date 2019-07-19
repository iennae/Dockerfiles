#  docker build -t sigje/hugo .
#  docker run --rm -v `pwd`:/pwd/ -p 1313:1313/tcp -it sigje/hugo
FROM alpine:latest
ENV HUGO_VERSION 0.55.6
LABEL maintainer iennae@gmail.com

RUN apk --no-cache add ca-certificates curl tar bash vim git tree

RUN curl -L https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_${HUGO_VERSION}_Linux-64bit.tar.gz | tar -zOxf - hugo > /usr/bin/hugo && chmod +x /usr/bin/hugo

WORKDIR /pwd/
EXPOSE 1313

CMD hugo server --bind="0.0.0.0" 
