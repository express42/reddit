FROM ruby:2.4

WORKDIR /app
COPY . /app

RUN apt-get update -qq && \
    apt-get install -y --no-install-recommends \
    build-essential && \
    dnsutils && \
    bundle install && \
    rm -rf /var/lib/apt/lists/*

ENV POST_SERVICE_HOST post
ENV POST_SERVICE_PORT 5000
ENV COMMENT_SERVICE_HOST comment
ENV COMMENT_SERVICE_PORT 9292

CMD ["puma"]
