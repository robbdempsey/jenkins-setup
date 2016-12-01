
FROM jenkins:2.19.3
MAINTAINER robb dempsey <robb.dempsey@gmail.com>

USER root
RUN apt-get -yqq update 
# install the docker client
RUN apt-get -yqq install docker.io
# add jenkins user to the docker group
RUN usermod -g docker jenkins
# add jenkins to root since it should matter in the container
RUN usermod -g root jenkins

# Grab gosu for easy step-down from root.
ADD https://github.com/tianon/gosu/releases/download/1.5/gosu-amd64 /usr/local/bin/gosu

RUN chmod 755 /usr/local/bin/gosu

VOLUME /var/run/docker.sock

ENTRYPOINT gosu jenkins /bin/tini -- /usr/local/bin/jenkins.sh
