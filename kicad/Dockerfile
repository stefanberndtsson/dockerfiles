FROM debian:bullseye-slim
LABEL maintainer "Jessie Frazelle <jess@linux.com>"

RUN apt-get update && apt-get install -y \
	kicad \
	--install-recommends \
	&& rm -rf /var/lib/apt/lists/*

RUN groupadd -g 998 wheel \
 && useradd -m -u 1000 -g 998 appuser

USER appuser
WORKDIR /home/appuser

ENTRYPOINT [ "kicad" ]
