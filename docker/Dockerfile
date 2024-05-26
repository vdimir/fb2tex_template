FROM texlive/texlive

RUN apt-get update && apt-get install -y \
    texlive-xetex \
    texlive-luatex \
    texlive-lang-cyrillic \
    texlive-fonts-recommended \
    texlive-fonts-extra \
    texlive-font-utils \
    && rm -rf /var/lib/apt/lists/*

RUN apt-get update && apt-get install -y \
    wget unzip

RUN wget -O /tmp/google-fonts.zip https://github.com/google/fonts/archive/main.zip \
    && unzip /tmp/google-fonts.zip -d /tmp \
    && mkdir -p /usr/share/fonts/truetype/google-fonts

RUN find /usr/share/fonts -type f -name "*.woff" -delete \
    && find /usr/share/fonts -type f -name "*.woff2" -delete

RUN find /tmp/fonts-main -type f \( -name "*.ttf" -o -name "*.otf" \) \
  | grep -iP "(open_sans|cormorant|lora|open_sans)" \
  | xargs -I {} cp {} /usr/share/fonts/truetype/google-fonts/ \
    && rm /tmp/google-fonts.zip \
    && fc-cache -fv

RUN apt-get update && apt-get install -y \
    fonts-ebgaramond \
    fonts-ebgaramond-extra

WORKDIR /work
