FROM qmcgaw/reactdevcontainer:debian
# upgrade using apt
RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y curl gpg

# Install Node.js
RUN curl -fsSL https://deb.nodesource.com/setup_20.x | bash - \
  && apt-get install -y nodejs

# Install fish
RUN echo 'deb http://download.opensuse.org/repositories/shells:/fish:/release:/3/Debian_11/ /' | tee /etc/apt/sources.list.d/shells:fish:release:3.list \
  && curl -fsSL https://download.opensuse.org/repositories/shells:fish:release:3/Debian_11/Release.key | gpg --dearmor | tee /etc/apt/trusted.gpg.d/shells_fish_release_3.gpg > /dev/null \
  && apt update \
  && apt install -y fish \
  && omf install bobthefish \
  && set -g theme_powerline_fonts no


