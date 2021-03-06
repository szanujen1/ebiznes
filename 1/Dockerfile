FROM ubuntu:18.04

RUN apt-get update && apt-get upgrade -y

RUN apt-get install -y openjdk-8-jdk wget curl gnupg2

RUN apt-get remove scala-library scala && \
    wget https://scala-lang.org/files/archive/scala-2.12.13.deb && \
    dpkg -i scala-2.12.13.deb && \
    apt-get update

RUN echo "deb https://dl.bintray.com/sbt/debian /" | tee -a /etc/apt/sources.list.d/sbt.list && \
    curl -sL "https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x2EE0EA64E40A89B84B2DF73499E82A75642AC823" | apt-key add && \
    apt-get update && \
    apt-get install -y sbt

RUN apt-get install -y npm

RUN npm --version && \
    java -version && \
    scala -version && \
    sbt about -Dsbt.rootdir=true
