FROM openshift/base-centos7:latest

MAINTAINER Christopher.Beyers@delta.com>

ENV OC_CLIENT_MIRROR https://mirror.openshift.com/pub/openshift-v4/clients/oc/4.2.10-201911290432.git.0.888f9c6.el7/linux/oc.tar.gz
ENV PYTHON_37_MIRROR https://www.python.org/ftp/python/3.7.5/Python-3.7.5.tgz

RUN curl $OC_CLIENT_MIRROR | tar -C /usr/local/bin/ -xzf -
RUN curl $PYTHON_37_MIRROR | tar -C /usr/local/bin/ -xzf -
