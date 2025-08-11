FROM ruby:3.2-slim

WORKDIR /app

RUN apt-get update && apt-get install -y \
    build-essential \
    libpq-dev \
    nodejs \
    && rm -rf /var/lib/apt/lists/*

COPY Gemfile Gemfile.lock ./

RUN bundle install

COPY . .

RUN bundle exec rails assets:precompile

EXPOSE 3000

RUN adduser --disabled-password --gecos '' railsuser
USER railsuser

CMD ["bundle", "exec", "rails", "server", "-b", "0.0.0.0"]