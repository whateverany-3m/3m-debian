ARG SOURCE_GROUP
ARG SOURCE_REGISTRY
ARG SOURCE_IMAGE
ARG SOURCE_VERSION

FROM $SOURCE_REGISTRY$SOURCE_GROUP$SOURCE_IMAGE:$SOURCE_VERSION

COPY src/rootfs/ /

RUN set -x ;\
  echo "INFO: begin RUN" ;\
  apt-get update ;\
  apt-get install -y --no-install-recommends \
    busybox-static=1:1.30.1-6+b3 \
    kubernetes-client=1.20.5+really1.20.2-1 \
    make=4.3-4.1 \
    ;\
  busybox --install ;\
  rm -rf /tmp/* /tmp/[!.]* /var/lib/apt/lists/* ;\
  apt-get autoremove -y ;\
  echo "INFO: end RUN"

