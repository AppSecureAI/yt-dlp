ARG BUILDIMAGE=ghcr.io/yt-dlp/manylinux2014_x86_64-shared:latest
ARG VERIFYIMAGE=alpine:3.22


FROM $BUILDIMAGE AS build

WORKDIR /yt-dlp
COPY --chown=nobody:nobody build.sh /build.sh
RUN chown -R nobody:nobody /yt-dlp
USER nobody
ENTRYPOINT ["/build.sh"]


FROM $VERIFYIMAGE AS verify

WORKDIR /testing
COPY --chown=nobody:nobody verify.sh /verify.sh
RUN chown -R nobody:nobody /testing
USER nobody
ENTRYPOINT ["/verify.sh"]
