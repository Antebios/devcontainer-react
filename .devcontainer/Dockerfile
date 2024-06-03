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
  && apt-get install fonts-powerline \
  && set -g theme_powerline_fonts no \
  && set -g theme_nerd_fonts yes \
  && set -g theme_display_git_ahead_verbose yes \
  && sset -g theme_display_git_stashed_verbose yes \
  && sset -g theme_display_git_default_branch yes \
  && sset -g theme_date_timezone America/Chicago

