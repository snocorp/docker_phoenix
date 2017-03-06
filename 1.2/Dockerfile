FROM elixir:1.4.0


# Install hex
RUN mix local.hex --force

# Install rebar
RUN mix local.rebar --force

ENV PHOENIX_VERSION 1.2.1

# install the Phoenix Mix archive
RUN mix archive.install --force https://github.com/phoenixframework/archives/raw/master/phoenix_new-$PHOENIX_VERSION.ez

# install Node.js (>= 6.0.0) and NPM in order to satisfy brunch.io dependencies
# See http://www.phoenixframework.org/docs/installation#section-node-js-5-0-0-
RUN curl -sL https://deb.nodesource.com/setup_6.x | bash - && apt-get install -y nodejs

VOLUME /root/.cache

WORKDIR /app
