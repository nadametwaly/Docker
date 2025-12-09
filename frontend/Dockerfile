FROM nginx:alpine
ARG FRONTEND_URL= https://www.tooplate.com/zip-templates/2134_gotto_job.zip 
ARG NGINX_USER=nginx_user
LABEL description="Web application served by nginx"
USER nginx_app
RUN addgroup -S nginx_app && adduser -S nginx_app -G nginx_app
ADD ${FRONTEND_URL} /usr/share/nginx/html/
RUN rm -rf /usr/share/nginx/html/*
RUN chown -R nginx_app:nginx_app \
    /usr/share/nginx/html \
    /var/log/nginx \
    /var/cache/nginx \
    /var/run/
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
