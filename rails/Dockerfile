FROM ruby:2.7
RUN apt-get update -qq && apt-get install -y nodejs postgresql-client
WORKDIR /project
COPY project/Gemfile /project/Gemfile
COPY project/Gemfile.lock /project/Gemfile.lock
RUN bundle install
COPY project /project

# Add a script to be executed every time the container starts.
COPY project/entrypoint.sh /usr/bin/
RUN chmod +x /usr/bin/entrypoint.sh
ENTRYPOINT ["entrypoint.sh"]
EXPOSE 3000

# Start the main process.
CMD ["rails", "server", "-b", "0.0.0.0"]
