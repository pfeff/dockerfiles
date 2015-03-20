FROM ubuntu:14.04

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get -qq update
RUN apt-get -qq upgrade
RUN apt-get -qq install ruby
RUN apt-get -qq install tmux
RUN apt-get -qq install zsh

RUN groupadd --gid 120 admin
RUN useradd matt --uid 1000 -G admin -s /bin/zsh

RUN gem install tmuxinator

WORKDIR /home/matt
USER matt


