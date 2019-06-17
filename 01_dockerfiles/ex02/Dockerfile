FROM ruby

RUN apt-get update -y && apt-get upgrade -y
RUN gem install rails
RUN apt-get install nodejs -y

ONBUILD ADD . /opt/app

ONBUILD WORKDIR /opt/app

ONBUILD RUN bundle install
ONBUILD RUN rails db:migrate
ONBUILD RUN rails db:seed
