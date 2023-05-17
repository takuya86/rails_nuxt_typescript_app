FROM ruby:3.2.1

ENV LANG C.UTF-8
ENV TZ Asia/Tokyo

RUN apt-get update -qq && apt-get install -y build-essential

RUN mkdir /app
WORKDIR /app

# GemfileとGemfile.lockをコピーしてGemをインストールします
COPY Gemfile Gemfile.lock ./
RUN gem install bundler
RUN bundle install

RUN bundle install

COPY . /app