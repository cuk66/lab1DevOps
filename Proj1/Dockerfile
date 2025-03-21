FROM nginx:alpine

COPY nginx/nginx.conf /etc/nginx/conf.d/default.conf

WORKDIR /app

RUN chown -R nginx:nginx /app && chmod -R 755 /app && \
        chown -R nginx:nginx /var/cache/nginx && \
        chown -R nginx:nginx /var/log/nginx && \
        chown -R nginx:nginx /etc/nginx/conf.d
RUN touch /var/run/nginx.pid && \
        chown -R nginx:nginx /var/run/nginx.pid

VOLUME /var/www/html

EXPOSE 8080

USER nginx

CMD ["nginx", "-g", "daemon off;"]