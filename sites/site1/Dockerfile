FROM ruby:2.5.1

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        postgresql-client nodejs \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /usr/src/app
COPY Gemfile* ./
RUN bundle install
COPY . .

EXPOSE 80
CMD ["rails", "server", "-p", "80", "-b", "0.0.0.0"]
