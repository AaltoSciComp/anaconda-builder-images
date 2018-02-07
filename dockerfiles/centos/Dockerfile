FROM centos:centos7

RUN yum install -y epel-release           \
  && yum update -y                        \
  && yum clean all

RUN yum groups mark install "Development Tools" \
  && yum groups mark convert "Development Tools" \
  && yum groupinstall -y "Development Tools" \
  && yum clean all

RUN yum update -y && yum install -y       \
  bash-completion                         \
  cmake                                   \
  curl                                    \
  git                                     \
  Lmod                                    \
  openssh                                 \
  python                                  \
  python-yaml                             \
  tcl                                     \
  wget                                    \
  which                                   \
  && yum clean all

RUN mkdir /build

COPY ./lmod.lmodrc.lua /etc/lmod.lmodrc.lua

COPY ./entry.sh /entry.sh

ENTRYPOINT ["/entry.sh"]

RUN yum update -y                         \
  && yum upgrade -y                       \
  && yum clean all
