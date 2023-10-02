FROM rust:1

LABEL maintainer="Supphachoke Suntiwichaya <mrchoke@gmail.com>"

ENV TZ=Asia/Bangkok

RUN apt update \
  && apt install -y \
  locales \
  && apt clean

ENV MULTIDICT_NO_EXTENSIONS=1

RUN sed --in-place '/en_US.UTF-8/s/^#//' /etc/locale.gen  \
  &&  sed --in-place '/th_TH.UTF-8/s/^#//' /etc/locale.gen \
  && locale-gen

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV LC_ALL en_US.UTF-8


COPY ./app /app

WORKDIR /app/


EXPOSE 8000
CMD ["/start.sh"]
