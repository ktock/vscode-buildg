ARG FOO="init"
ARG AAA="init"

FROM ghcr.io/stargz-containers/busybox:1.32.0-org AS build1
RUN echo hello > /hello

FROM ghcr.io/stargz-containers/busybox:1.32.0-org AS build2
ARG FOO
ARG AAA
RUN echo hi > /hi

FROM scratch
COPY --from=build1 /hello /
RUN cat fail > /
COPY --from=build2 /hi /
