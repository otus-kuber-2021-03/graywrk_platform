FROM nginx:1.19

RUN mkdir /app && \
    chown -R 1001:1001 /app && \
    chmod -R 740 /app && \
    chown -R 1001:1001 /var/cache/nginx && \
    chown -R 1001:1001 /var/log/nginx && \
    chown -R 1001:1001 /etc/nginx/conf.d && \
    touch /var/run/nginx.pid && \
    chown -R 1001:1001 /var/run/nginx.pid

USER 1001:1001

EXPOSE 8000

COPY ./default.conf.template /etc/nginx/conf.d/default.conf
COPY ./app/* /app/

ENTRYPOINT ["nginx", "-g", "daemon off;"]
