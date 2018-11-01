FROM centos:7

MAINTAINER Nikolaos Vyzas <pondix@gmail.com>

RUN echo -e "[proxysql_repo]\nname= ProxySQL YUM repository\nbaseurl=http://repo.proxysql.com/ProxySQL/proxysql-1.4.x/centos/\$releasever\ngpgcheck=1\ngpgkey=http://repo.proxysql.com/ProxySQL/repo_pub_key" > /etc/yum.repos.d/proxysql.repo && yum -y install https://github.com/sysown/proxysql/releases/download/v2.0.0-rc2/proxysql-rc2-2.0.0-1-centos7.x86_64.rpm && mkdir /var/lib/proxysql && yum clean all

ENTRYPOINT ["proxysql", "-f", "-D", "/var/lib/proxysql"]
