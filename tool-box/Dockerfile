FROM openshift/base-centos7:latest

MAINTAINER Christopher.Beyers@delta.com>

ENV OC_CLIENT_MIRROR https://mirror.openshift.com/pub/openshift-v4/clients/oc/4.2.10-201911290432.git.0.888f9c6.el7/linux/oc.tar.gz

RUN curl $OC_CLIENT_MIRROR | tar -C /usr/local/bin/ -xzf -

WORKDIR $HOME

ADD ./root /

RUN chmod u+x /usr/local/bin/run

USER 1001

ENTRYPOINT ["/usr/local/bin/run"]
CMD ["sleep", "infinity"]
