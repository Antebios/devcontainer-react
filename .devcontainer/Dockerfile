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
  && apt install -y fish fonts-powerline

WORKDIR /root
# RUN curl https://raw.githubusercontent.com/oh-my-fish/oh-my-fish/master/bin/install | /usr/bin/fish --init-command 'set argv -- --noninteractive'
RUN curl https://raw.githubusercontent.com/oh-my-fish/oh-my-fish/master/bin/install > install \
  && /usr/bin/fish install --noninteractive

ENTRYPOINT [ "/usr/bin/fish" ]

RUN fish -c "omf install bobthefish" \
  && fish -c "set -g theme_powerline_fonts no" \
  && fish -c "set -g theme_nerd_fonts yes" \
  && fish -c "set -g theme_display_git_ahead_verbose yes" \
  && fish -c "set -g theme_display_git_stashed_verbose yes" \
  && fish -c "set -g theme_display_git_default_branch yes" \
  && fish -c "set -g theme_date_timezone America/Chicago"

