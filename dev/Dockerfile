FROM ubuntu:14.04

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get -qq update
RUN apt-get -qq upgrade

RUN apt-get -qq install curl
RUN apt-get -qq install git
RUN apt-get -qq install ruby
RUN apt-get -qq install telnet
RUN apt-get -qq install tmux
RUN apt-get -qq install vim
RUN apt-get -qq install vim-syntax-docker
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

RUN git clone https://github.com/pfeff/dotfiles.git dotfiles
RUN ln -s ~/dotfiles/zshrc .zshrc
RUN ln -s ~/dotfiles/tmux.conf .tmux.conf
RUN ln -s ~/dotfiles/tmuxinator .tmuxinator
RUN ln -s ~/dotfiles/vim .vim
RUN ln -s ~/dotfiles/vimrc .vimrc

RUN git config --global user.email "matthew.pfefferle@gmail.com"
RUN git config --global user.name "Matt Pfefferle"

CMD /bin/zsh
