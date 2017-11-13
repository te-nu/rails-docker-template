FROM ruby:2.4

RUN apt-get update -qq && apt-get -y install mysql-client

WORKDIR /tmp

COPY Gemfile Gemfile
COPY Gemfile.lock Gemfile.lock

RUN gem update bundler && bundle install --jobs=2 && \
    mkdir /app

WORKDIR /app

EXPOSE 3000
CMD ["rails", "s", "-b", "0.0.0.0"]
