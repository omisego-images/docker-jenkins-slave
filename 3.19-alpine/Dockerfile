FROM jenkinsci/jnlp-slave:3.19-1-alpine
MAINTAINER Kridsada Thanabulpong <sirn@omise.co>

ENV CLOUDSDK_CORE_DISABLE_PROMPTS 1
ENV PATH /opt/google-cloud-sdk/bin:$PATH

USER root

RUN set -xe && \
    apk add --update --no-cache docker

RUN set -xe && \
    apk add --update --no-cache curl python && \
    curl https://sdk.cloud.google.com | bash && \
    mkdir -p /opt && \
    mv google-cloud-sdk /opt && \
    gcloud components install kubectl

USER ${user}
