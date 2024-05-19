FROM texlive/texlive

RUN apt-get update && apt-get install -y \
    texlive-xetex \
    texlive-luatex \
    texlive-lang-cyrillic \
    && rm -rf /var/lib/apt/lists/*


RUN apt-get update && apt-get install -y \
    texlive-fonts-extra  \
    texlive-fonts-extra \
    texlive-font-utils


RUN apt-get update && apt-get install -y \
    texlive-fonts-recommended

RUN apt-get update && apt-get install -y \
    wget unzip

RUN echo 'Install Fonts' \
    && wget -O /tmp/Cormorant.zip "https://github.com/CatharsisFonts/Cormorant/archive/refs/heads/master.zip" && unzip /tmp/Cormorant.zip -d /usr/local/share/fonts/Cormorant && mkdir -p /usr/local/share/fonts/Cormorant && mv /usr/local/share/fonts/Cormorant/Cormorant-master/fonts/otf/* /usr/local/share/fonts/Cormorant/ \
    && wget -O /tmp/great-vibes.zip "https://github.com/googlefonts/great-vibes/archive/refs/heads/master.zip" && unzip /tmp/great-vibes.zip -d /usr/local/share/fonts/GreatVibes && mkdir -p /usr/local/share/fonts/GreatVibes && mv /usr/local/share/fonts/GreatVibes/great-vibes-master/fonts/ttf/* /usr/local/share/fonts/GreatVibes/ \
    && rm -rf /usr/local/share/fonts/great-vibes-master/fonts/webfonts \
    && rm -rf /usr/local/share/fonts/Cormorant/Cormorant-master/fonts/webfonts \
    && fc-cache -fv

WORKDIR /work
