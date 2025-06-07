

# based on https://docs.openolat.org/manual_admin/installation/installGuide/
# Use an Ubuntu-based Tomcat image with JDK 17
FROM tomcat:jdk17-openjdk

# Update package repository and install necessary packages.
RUN apt-get update && \
  apt-get install -y unzip && \
  apt-get clean

# Create an OpenOLAT user
RUN useradd -m -s /bin/bash openolat

# Download and extract openolat war
RUN curl -fSs https://www.openolat.com/releases/openolat_2003.war -o openolat.war && \
  unzip -d ${CATALINA_HOME}/webapps/ROOT openolat.war && \
  rm openolat.war

# Add OpenOLAT configuration files
COPY log4j2.xml ${CATALINA_HOME}/lib/
COPY olat.local.properties ${CATALINA_HOME}/lib/
COPY ROOT.xml ${CATALINA_HOME}/conf/Catalina/localhost/ 
COPY server.xml ${CATALINA_HOME}/conf/

# Switch to the OpenOLAT user
USER openolat
