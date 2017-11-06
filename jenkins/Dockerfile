FROM jenkins/jenkins:2.60.3

USER root

# Install maven package
ENV MAVEN_VERSION 3.3.9
RUN cd /usr/local; wget -q -O - http://mirrors.ibiblio.org/apache/maven/maven-3/$MAVEN_VERSION/binaries/apache-maven-$MAVEN_VERSION-bin.tar.gz | tar xvfz - && \
    ln -sv /usr/local/apache-maven-$MAVEN_VERSION /usr/local/maven

USER jenkins

# Install plugins
RUN /usr/local/bin/install-plugins.sh mock-slave workflow-aggregator blueocean hipchat

# Add configuration 
ADD JENKINS_HOME /usr/share/jenkins/ref
