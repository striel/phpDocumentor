FROM nginx:alpine

ARG VERSION="latest"

RUN ln -sf /dev/stdout /var/log/nginx/access.log \
 && ln -sf /dev/stderr /var/log/nginx/error.log

COPY .build /usr/share/nginx/html/$VERSION
COPY nginx.conf /etc/nginx/conf.d/default.conf
COPY .static/redirectToLatest.html /usr/share/nginx/html/index.html
COPY .static/redirectToLatest.html /usr/share/nginx/html/404.html

STOPSIGNAL SIGQUIT
