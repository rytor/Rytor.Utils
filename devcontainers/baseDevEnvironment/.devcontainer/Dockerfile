FROM ubuntu:noble

# Install dependencies
RUN apt update && apt install -y \
    eza \
    bat \
    fzf \
    ripgrep \
    zoxide \
    entr \
    mc

RUN curl -sS https://starship.rs/install.sh | sh
