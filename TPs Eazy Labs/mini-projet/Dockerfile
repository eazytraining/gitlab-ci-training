FROM ubuntu:18.04 as files
LABEL maintainer='TCHASSEM ANSELME'
RUN apt-get update
RUN DEBIAN_FRONTEND=noninteractive apt-get install git -y
RUN mkdir /opt/files
RUN git clone https://github.com/daviddias/static-webpage-example.git /opt/files/ 

FROM nginx:stable-alpine3.17-slim
LABEL maintainer='TCHASSEM ANSELME'
COPY --from=files /opt/files/src/ /usr/share/nginx/html/
ENTRYPOINT ["/docker-entrypoint.sh"]
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]