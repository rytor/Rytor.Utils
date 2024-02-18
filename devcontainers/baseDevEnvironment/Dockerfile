FROM ubuntu:latest

ENV DEBIAN_FRONTEND=noninteractive

# get latest security updates
RUN apt update && \
	apt upgrade -y

# install git
RUN apt install git-all -y

# install docker
RUN apt-get update && \
	apt-get install ca-certificates curl -y && \
	install -m 0755 -d /etc/apt/keyrings && \
	curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc && \
	chmod a+r /etc/apt/keyrings/docker.asc

RUN echo \
  	"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  	$(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  	tee /etc/apt/sources.list.d/docker.list > /dev/null && \
	apt-get update

RUN apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y

# install code cli
RUN apt-get install wget gpg -y && \
	wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg && \
	install -D -o root -g root -m 644 packages.microsoft.gpg /etc/apt/keyrings/packages.microsoft.gpg && \
	sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list' && \
	rm -f packages.microsoft.gpg

RUN apt install apt-transport-https -y && \
	apt update && \
	apt install code -y

# install .NET
RUN apt-get update && \
  	apt-get install -y dotnet-sdk-8.0

# install nvm
RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash

# install neovim
RUN apt install neovim -y

# install tmux
RUN apt-get update && \
	apt-get install tmux -y
