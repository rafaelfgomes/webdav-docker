FROM ubuntu

ARG DAVUSER
ARG DAVPASS
ARG TMPFOLDER

RUN apt update && apt install nginx-full openssl -y

RUN sed -i '/gzip_/ s/#\ //g' /etc/nginx/nginx.conf

COPY ./configs/webdav.conf /etc/nginx/conf.d/default.conf

RUN rm /etc/nginx/sites-enabled/default

RUN echo -n $DAVUSER':' | tee /etc/nginx/.passwords.list
RUN openssl passwd -apr1 -salt davserver $DAVPASS | tee -a /etc/nginx/.passwords.list

RUN mkdir $TMPFOLDER && chown -R www-data:www-data $TMPFOLDER

EXPOSE 80
EXPOSE 443

CMD ["nginx", "-g", "daemon off;"]
