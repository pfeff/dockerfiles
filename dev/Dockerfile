FROM ubuntu:14.04

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get -qq update
RUN apt-get -qq upgrade

RUN apt-get -qq install curl
RUN apt-get -qq install git
RUN apt-get -qq install ruby
RUN apt-get -qq install telnet
RUN apt-get -qq install tmux
RUN apt-get -qq install wget
RUN apt-get -qq install wget
RUN apt-get -qq install zsh

RUN groupadd --gid 120 admin
RUN useradd matt --uid 1000 -G admin -s /bin/zsh -m

RUN gem install tmuxinator

WORKDIR /home/matt
USER matt

ENV ZSH /home/matt/.oh-my-zsh
RUN git clone https://github.com/robbyrussell/oh-my-zsh.git ${ZSH}

RUN git clone https://github.com/pfeff/dotfiles.git src/github/pfeff/dotfiles
RUN ln -s ~/src/github/pfeff/dotfiles/zshrc .zshrc
RUN ln -s ~/src/github/pfeff/dotfiles/tmux.conf .tmux.conf
RUN ln -s ~/src/github/pfeff/dotfiles/vim .vim
RUN ln -s ~/src/github/pfeff/dotfiles/vimrc .vimrc

CMD /bin/zsh
