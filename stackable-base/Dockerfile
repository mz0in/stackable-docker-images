# 8.9-1029 as of 2023-12-01
FROM registry.access.redhat.com/ubi8/ubi-minimal:8.9@sha256:0e1879febd1be94e0d234060770ce33a543488374d91881259de9119ea75d33f

# intentionally unused
ARG PRODUCT

RUN microdnf update && \
    microdnf --assumeyes install shadow-utils && \
    groupadd --gid 1000 --system stackable && \
    useradd --gid stackable --uid 1000 --system stackable -d /stackable && \
    mkdir /stackable && \
    chown stackable:stackable /stackable && \
    microdnf remove shadow-utils && \
    microdnf clean all && \
    echo "alias ll='ls -alF --color=auto'" >> /etc/profile.d/00-aliases.sh
