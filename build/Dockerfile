FROM registry.access.redhat.com/ubi7/ubi-minimal:latest

ENV OPERATOR=/usr/local/bin/tekton-operator \
    USER_UID=1001 \
    USER_NAME=tekton-operator

# install operator binary
COPY build/_output/bin/operator ${OPERATOR}

COPY build/bin /usr/local/bin
RUN  /usr/local/bin/user_setup

COPY deploy/resources /deploy/resources

ENTRYPOINT ["/usr/local/bin/entrypoint"]

USER ${USER_UID}
