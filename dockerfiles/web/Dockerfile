FROM nginx:latest

RUN apt-get update && apt-get install -y \
   vim \
   zip \
   unzip \
   iputils-ping \
   git
RUN git clone https://github.com/en-siba/laravel-sample.git /var/www/public
ADD ./dockerfiles/web/default.conf /etc/nginx/conf.d/default.conf

EXPOSE 80
