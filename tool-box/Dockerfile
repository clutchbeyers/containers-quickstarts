FROM openshift/base-centos7:latest

MAINTAINER Christopher.Beyers@delta.com>

ENV OC_CLIENT_MIRROR https://mirror.openshift.com/pub/openshift-v4/clients/oc/4.2.10-201911290432.git.0.888f9c6.el7/linux/oc.tar.gz
ENV HOME /home/tool-box

RUN curl $OC_CLIENT_MIRROR | tar -C /usr/local/bin/ -xzf -
RUN git clone https://github.com/pyenv/pyenv.git $HOME/.pyenv

RUN yum -y install epel-release
RUN yum -y install git gcc zlib-devel bzip2-devel readline-devel sqlite-devel openssl-devel
RUN yum clean all

COPY .bashrc $HOME/.bashrc

RUN source $HOME/.bashrc

ENV PYENV_ROOT="$HOME/.pyenv"
ENV PATH="$PYENV_ROOT/bin:$PATH"

RUN pyenv install 3.7.5

WORKDIR $HOME

ADD ./root /

RUN chmod u+x /usr/local/bin/run

USER 1001

ENTRYPOINT ["/usr/local/bin/run"]
CMD ["sleep", "infinity"]
