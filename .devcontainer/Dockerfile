FROM ubuntu:20.04

# SHELL ["/bin/bash", "-c"]

# RUN apt-get update && apt-get upgrade &&
RUN apt-get update && apt-get -y install curl git

RUN git clone https://github.com/OiNutter/nodenv /usr/local/nodenv
RUN mkdir -p /usr/local/nodenv/plugins
RUN echo 'export NODENV_ROOT=/usr/local/nodenv' > /etc/profile.d/nodenv.sh
RUN echo 'export PATH=$NODENV_ROOT/bin:$PATH' >> /etc/profile.d/nodenv.sh
RUN echo 'eval "$(nodenv init -)"'  >> /etc/profile.d/nodenv.sh

RUN echo 'eval "$(nodenv init -)"'
RUN git clone https://github.com/nodenv/node-build.git /usr/local/nodenv/plugins/node-build

# RUN git clone https://github.com/nodenv/nodenv.git ~/.nodenv
# RUN echo 'export PATH="$HOME/.nodenv/bin:$PATH"' >> ~/.bashrc
# RUN echo 'eval "$(nodenv init -)"' >> ~/.bashrc
# RUN source ~/.bashrc
# RUN echo "$(nodenv root)"
# RUN mkdir -p "$(nodenv root)"/plugins
# RUN git clone https://github.com/nodenv/node-build.git "$(nodenv root)"/plugins/node-build

# RUN /usr/local/nodenv/bin/nodenv install 18.12.0
# RUN nodenv global 18.12.0