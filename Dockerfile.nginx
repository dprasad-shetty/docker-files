FROM nginx:alpine

COPY ./public /usr/share/nginx/html

COPY nginx.conf /etc/nginx/nginx.conf

RUN addgroup -g 1001 -S nginx && \
    adduser -S -D -H -u 1001 -h /var/cache/nginx -s /sbin/nologin -G nginx -g nginx nginx

EXPOSE 80

USER nginx

CMD ["nginx", "-g", "daemon off;"]