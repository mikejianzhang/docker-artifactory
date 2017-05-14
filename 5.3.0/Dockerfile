FROM tomcat:8.0.43-jre8

MAINTAINER Matthias Grüter <matthias@grueter.name>

# To update, check https://bintray.com/jfrog/artifactory/artifactory/view
ENV ARTIFACTORY_VERSION 5.3.0
ENV ARTIFACTORY_SHA1 245aeb7b2d77830462067d5a19c3bd32ae014ddf

# Disable Tomcat's manager application.
RUN rm -rf webapps/*

COPY artifactory.war $CATALINA_HOME/webapps/artifactory.war

# Expose tomcat runtime options through the RUNTIME_OPTS environment variable.
#   Example to set the JVM's max heap size to 256MB use the flag
#   '-e RUNTIME_OPTS="-Xmx256m"' when starting a container.
RUN echo 'export CATALINA_OPTS="$RUNTIME_OPTS"' > bin/setenv.sh

# Artifactory home
RUN mkdir -p /artifactory
ENV ARTIFACTORY_HOME /artifactory

# Expose Artifactories data, log and backup directory.
VOLUME /artifactory

WORKDIR /artifactory
# Add hook to install custom artifactory.war (i.e. Artifactory Pro) to replace OSS distribution.
#ONBUILD COPY artifactory.war $CATALINA_HOME/webapps/artifactory.war