FROM ruby:2.5-alpine3.8
RUN apk --update --no-cache add openssh git zip make docker g++
RUN gem install hako -v 2.3.1 -N --no-rdoc --no-ri
RUN rm -rf /root/.cache
