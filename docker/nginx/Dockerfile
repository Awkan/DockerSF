FROM ubuntu:16.04
ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get -y upgrade && apt-get install -y curl sudo nginx

CMD ["nginx", "-g", "daemon off;"]
