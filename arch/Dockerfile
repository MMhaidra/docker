FROM dock0/arch

MAINTAINER Andrea Rigoni

ENV http_proxy 'eproxy2.rfx.local:8080'
ENV https_proxy 'eproxy2.rfx.local:8080'

# RUN     printf "\n \
#    export RFX_PROXY='eproxy2.rfx.local:8080' \n \
#    export http_proxy=\${RFX_PROXY} \n \
#    export https_proxy=\${RFX_PROXY} \n \
#    export  ftp_proxy=\${RFX_PROXY} \n \
#    export HTTP_PROXY=\${RFX_PROXY} \n \
#    export HTTPS_PROXY=\${RFX_PROXY} \n \
#    export  FTP_PROXY=\${RFX_PROXY} \n " >> /etc/profile.d/proxy.sh; \
#    chmod 777 /etc/profile.d/proxy.sh;


COPY pkg /pkg

RUN pacman -S --needed --noconfirm base-devel wget tar gzip yajl; 

RUN pacman -U --noconfirm /pkg/package-query-1.6.2-1-x86_64.pkg.tar.xz; \
    pacman -U --noconfirm /pkg/yaourt-1.6-1-any.pkg.tar.xz; \
    useradd -m pkg; \
    printf "\n pkg ALL=(ALL) NOPASSWD: ALL \n Defaults env_keep += \"http_proxy ftp_proxy https_proxy\"\n" >> /etc/sudoers;
    

    



