FROM ft-rails:on-build

EXPOSE 3000

CMD ["rails", "s", "-b", "0.0.0.0", "-p", "3000"]


# For Sample App:
# git clone https://bitbucket.org/railstutorial/sample_app_4th_ed.git app
# cd app
# bundle install --without production

# Building Project:
# docker build -t ft-rails:on-build ./ft-rails      — Build image from your Dockerfile
# docker build -t ex02 .                            — Build image from given Dockerfile
# docker run -it --rm -p 3000:3000 ex02             — Run image