FROM debian:sid-slim

RUN apt-get update \
 && apt-get install -y libfreetype6 libcups2 libglib2.0-0 libglu1-mesa libsm6 libxrender1 libfontconfig1 libxext6 libxcb1 xdg-utils wget \
 && wget -O /root/wps-office_11.1.0.9505.XA_amd64.deb http://wdl1.pcfg.cache.wpscdn.com/wpsdl/wpsoffice/download/linux/9505/wps-office_11.1.0.9505.XA_amd64.deb \
 && dpkg -i /root/wps-office_11.1.0.9505.XA_amd64.deb \
 && apt-get clean \
 && rm /root/wps-office_11.1.0.9505.XA_amd64.deb \
 && rm -rf /var/lib/apt/lists/*

CMD [ "echo", "Use one of the following commands [ wps | et | wpp ]" ]
