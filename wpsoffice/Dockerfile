FROM ubuntu:18.04

RUN apt-get update \
 && apt-get install -y libfreetype6 libcups2 libglib2.0-0 libglu1-mesa libsm6 libxrender1 libfontconfig1 libxext6 libxcb1 xdg-utils wget \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

RUN wget -O /root/wps-office_11.1.0.9505.XA_amd64.deb http://wdl1.pcfg.cache.wpscdn.com/wpsdl/wpsoffice/download/linux/9505/wps-office_11.1.0.9505.XA_amd64.deb \
 && dpkg -i /root/wps-office_11.1.0.9505.XA_amd64.deb \
 && rm /root/wps-office_11.1.0.9505.XA_amd64.deb \
 && groupadd -g 998 wheel \
 && useradd -m -u 1000 -g 998 appuser

USER appuser
WORKDIR /home/appuser

CMD [ "echo", "Use one of the following commands [ wps | et | wpp ]" ]
