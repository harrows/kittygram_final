FROM nginx:1.22.1
COPY --from=harrowsdocker/kittygram_frontend:latest /app/build /usr/share/nginx/html

COPY nginx.conf /etc/nginx/conf.d/default.conf

RUN mkdir -p /static /media
