FROM ruby:2.3.1

MAINTAINER "Bartosz 'tkaczu' Tkaczewski"

RUN apt-get update -qq && apt-get upgrade -qq
RUN apt-get install -yq curl git build-essential libpq-dev postgresql-client

RUN curl -sL https://deb.nodesource.com/setup | bash - && apt-get install -yq nodejs
RUN npm -g install npm@latest-2

RUN mkdir /up-app
ADD Gemfile /up-app/Gemfile
ADD Gemfile.lock /up-app/Gemfile.lock

WORKDIR /up-app
RUN bundle install

EXPOSE 3000

CMD /bin/bash