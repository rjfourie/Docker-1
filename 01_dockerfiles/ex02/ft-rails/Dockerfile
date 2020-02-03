FROM ruby:2.6

RUN	gem install rails sqlite3 &&\
	apt update &&\
	apt install nodejs -y

ONBUILD ADD	app /opt/app
ONBUILD WORKDIR	/opt/app
ONBUILD EXPOSE 3000
ONBUILD RUN	bundle install
ONBUILD RUN bundle exec rake db:migrate
ONBUILD RUN bundle exec rake db:seed