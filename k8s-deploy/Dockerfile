FROM ruby:2.3.3-slim
RUN apt-get update && apt-get install -yq git make build-essential
RUN mkdir /app
WORKDIR /app

ADD Gemfile Gemfile.lock /app/
RUN bundle config git.allow_insecure true && gem install bundler -v '= 1.14.6' && bundle install

ADD . /app

CMD bundle exec unicorn -p 6060