FROM ruby:3.1.2-alpine3.15
LABEL maintainer="dev@shigeki.tokyo"
ENV LANG C.UTF-8

WORKDIR /var/www

RUN apk upgrade --update \
    && apk --no-cache add --virtual .build-dependencies \
    build-base \
    make \
    g++ \
    gcc \
    libpng-dev \
    libzip-dev \
    libxml2-dev \
    libxslt-dev \
    postgresql-dev \
    && apk --no-cache add \
    libpq \
    libxml2 \
    libxslt \
    tzdata \
    tini \
    wget \
    unzip

ADD ./www/Gemfile /var/www/Gemfile
ADD ./www/Gemfile.lock /var/www/Gemfile.lock

RUN gem update --system \
    && bundle config set force_ruby_platform true \
    && bundle install \
    && apk del --purge .build-dependencies \
    && rm -rf /var/cache/apk/*

COPY ./docker/development/app/bootstrap /usr/bin/
RUN chmod +x /usr/bin/bootstrap

ENTRYPOINT ["/sbin/tini", "--"]
CMD ["bootstrap"]