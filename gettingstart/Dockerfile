FROM --platform=linux/amd64 mcr.microsoft.com/devcontainers/base:jammy

# [Optional] Uncomment this section to install additional OS packages.
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
     && apt-get -y install --no-install-recommends sudo curl
# RUN update-alternatives --set iptables /usr/sbin/iptables-legacy
# RUN update-alternatives --set ip6tables /usr/sbin/ip6tables-legacy

RUN curl -OL https://github.com/hyperledger/firefly-cli/releases/download/v1.3.1/firefly-cli_1.3.1_Linux_386.tar.gz
RUN tar -zxf ./firefly-cli_*.tar.gz -C /usr/local/bin ff && rm ./firefly-cli_*.tar.gz
RUN ff version

# RUN apt-get install -y build-essential pkg-config libudev-dev llvm libclang-dev protobuf-compiler libssl-dev
# RUN apt-get install -y libssl-dev libudev-dev pkg-config zlib1g-dev llvm clang cmake make libprotobuf-dev protobuf-compiler

# # 環境変数の設定
# ENV DOKCER_OPERATION_USER=solanauser
# ENV DOKCER_OPERATION_USERPASSWORD=solanauser
# ENV UID=1001
# ENV DOKCER_OPERATION_GROUP=solanauser
# # ユーザーを作成して切り替え
# ## dockerグループを作成
# RUN groupadd ${DOKCER_OPERATION_GROUP}
# ## dockerグループに所属するユーザーを作成
# RUN useradd -g ${DOKCER_OPERATION_GROUP} -u ${UID} ${DOKCER_OPERATION_USER} -m
# ## sudo権限付与
# RUN usermod -aG sudo ${DOKCER_OPERATION_USER}
# RUN echo ${DOKCER_OPERATION_USER}:${DOKCER_OPERATION_USERPASSWORD} | chpasswd && \
#     echo "${DOKCER_OPERATION_USER}   ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers


# USER root

# RUN echo "if [ -t 1 ]; then" >> /root/.bashrc
# RUN echo "exec zsh" >> /root/.bashrc
# RUN echo "fi" >> /root/.bashrc

# USER ${DOKCER_OPERATION_USER}

# RUN echo "if [ -t 1 ]; then" >> $HOME/.bashrc
# RUN echo "exec zsh" >> $HOME/.bashrc
# RUN echo "fi" >> $HOME/.bashrc

# ADD .zshrc $HOME/.zshrc


# # shellをbashに変更
# SHELL [ "/bin/bash", "-c" ]

# ### install node ###########

# ## ユーザーの切り替え
# USER ${DOKCER_OPERATION_USER}
# #### install nvm
# RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash

# #### install node
# RUN . $HOME/.nvm/nvm.sh && \
#     nvm install --lts && \
#     nvm use --lts && \
#     node -v && npm -v && \
#     npm i -g yarn

# SHELL [ "/bin/sh", "-c" ]

# ### install solana
# RUN sh -c "$(curl -sSfL https://release.solana.com/v1.18.18/install)"

# ### install rust, anchor ###########
# RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
# RUN . "$HOME/.cargo/env" && \ 
#     cargo install --git https://github.com/coral-xyz/anchor avm --tag v0.29.0 --locked --force && \
#     avm install 0.29.0 && avm use 0.29.0

