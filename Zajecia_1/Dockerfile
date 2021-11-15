FROM alpine:3.14
LABEL author jpalczewski
LABEL version 0.0.1
LABEL descriptiom just a weird nginx image

# /opt/custom_site
# stdout  = access, stderr = error


RUN     apk update \
        && apk add git curl wget nano nginx  \ 
        && ln -sf /dev/stdout /var/log/nginx/access.log \
        && ln -sf /dev/stderr /var/log/nginx/error.log  \
        && mkdir -p /opt/custom_site



COPY site/* /opt/custom_site
COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]


