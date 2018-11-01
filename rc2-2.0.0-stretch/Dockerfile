FROM debian:stretch

MAINTAINER Nikolaos Vyzas <pondix@gmail.com>

RUN apt-get update && apt-get install -y wget lsb-release gnupg && wget -O - 'http://repo.proxysql.com/ProxySQL/repo_pub_key' | apt-key add - && echo deb http://repo.proxysql.com/ProxySQL/proxysql-1.4.x/$(lsb_release -sc)/ ./ | tee /etc/apt/sources.list.d/proxysql.list && apt-get update && wget https://github.com/sysown/proxysql/releases/download/v2.0.0-rc2/proxysql-rc2_2.0.0-debian9_amd64.deb && apt -y install ./proxysql-rc2_2.0.0-debian9_amd64.deb && rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["proxysql", "-f", "-D", "/var/lib/proxysql"]
