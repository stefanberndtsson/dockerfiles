FROM debian:sid-slim
LABEL maintainer "Stefan Berndtsson <stefan.berndtsson@gmail.com>"

RUN apt-get update && apt-get install -y \
	dirmngr \
	gnupg \
	--no-install-recommends \
	&& apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 0AB215679C571D1C8325275B9BDB3D89CE49EC21 \
	&& echo "deb http://ppa.launchpad.net/mozillateam/firefox-next/ubuntu xenial main" >> /etc/apt/sources.list.d/firefox.list \
	&& apt-get update && apt-get install -y \
  rawtherapee \
	--no-install-recommends \
	&& rm -rf /var/lib/apt/lists/*

RUN groupadd -g 998 wheel \
 && useradd -m -u 1000 -g 998 appuser

ENV LANG en-US

USER appuser
WORKDIR /home/appuser

ENTRYPOINT [ "rawtherapee" ]
