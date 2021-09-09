FROM debian:buster-slim
RUN apt-get update && apt-get install -y curl gcc make && apt clean \
  && curl https://nginx.org/download/nginx-1.21.3.tar.gz | tar -xz \
  && cd ./nginx-1.21.3 \
  && ./configure --with-http_stub_status_module --without-http_rewrite_module \
  && make \
  && make install
FROM debian:buster-slim
COPY --from=0 /usr/local/nginx/ /usr/local/nginx/
COPY ./nginx.conf /usr/local/nginx/conf/nginx.conf
EXPOSE 8000
ENTRYPOINT ["/usr/local/nginx/sbin/nginx"]
CMD ["-g", "daemon off;"]