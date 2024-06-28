FROM ruby:3.1.6-bullseye

ARG UID=1000
ARG GID=1000

ENV GEM_HOME="/app/.bundle"
ENV PATH $GEM_HOME/bin:$GEM_HOME/gems/bin:$PATH

ENV BUNDLE_PATH="/app/.bundle"
ENV BUNDLE_PATH="/app/.bundle/bin"

RUN gem install bundler rails rake

ENV RAILS_ROOT /app
WORKDIR /app
RUN chown -R $USER:$USER /app

EXPOSE 3000

USER "${UID}:${GID}"

ENTRYPOINT ["/app/bin/docker-entrypoint.sh"]
CMD ["rails", "server"]