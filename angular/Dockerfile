FROM nginx:stable-alpine

RUN rm -rf /usr/share/nginx/html/*

COPY sistema-ventas-front/ /usr/share/nginx/html/
COPY nginx.conf /etc/nginx/nginx.conf
COPY mime.types /etc/nginx/mime.types

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]