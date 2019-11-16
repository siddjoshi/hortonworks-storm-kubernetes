FROM centos:7

RUN yum install -y java-1.7.0-openjdk java-1.7.0-openjdk-devel; \
    mkdir /usr/java; \
    ln -s /usr/hdp/current/jvm/java-1.7.0-openjdk-1.7.0.51.x86_64 /usr/java/default; \
    export JAVA_HOME=/usr/java/default; \
    export PATH=$JAVA_HOME/bin:$PATH; \
    yum install -y wget;

## Ambari 2.7.3
## Add Ambari Repo

RUN yum-config-manager --add-repo http://public-repo-1.hortonworks.com/ambari/centos7/2.x/updates/2.7.3.0/ambari.repo; \
    yum-config-manager --add-repo http://public-repo-1.hortonworks.com/HDP/centos7/3.x/updates/3.1.0.0/hdp.repo

RUN yum install -y ntp && chkconfig ntpd on

RUN yum install -y ambari-server