FROM openjdk:18.0.2

RUN mkdir -p /opt/ipcounter
COPY target/ipcounter-*.jar /opt/ipcounter
WORKDIR /opt/ipcounter
CMD cd /opt/ipcounter
