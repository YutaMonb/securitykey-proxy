FROM node:10.15-alpine

RUN apk --update add \
    python3 \
    wget \
    groff

RUN wget https://bootstrap.pypa.io/get-pip.py \
    && python3 get-pip.py

COPY web /var/www/html/web
WORKDIR /var/www/html

RUN cd ./web && npm install && cd ../
COPY start.sh /var/www/html
VOLUME /var/www/html
RUN chmod +x start.sh
