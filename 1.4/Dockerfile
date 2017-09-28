FROM debian:stretch

MAINTAINER Stephan Peijnik <speijnik@anexia-it.com

ARG dumb_init_version=1.2.0
ARG dumb_init_base_url=https://github.com/Yelp/dumb-init/releases/download/v${dumb_init_version}
ARG dumb_init_package_name=dumb-init_${dumb_init_version}_amd64.deb

ARG proxysql_version=1.4.3
ARG proxysql_base_url=https://github.com/sysown/proxysql/releases/download/v${proxysql_version}
ARG proxysql_package_name=proxysql_${proxysql_version}-debian9_amd64.deb

# Install wget so we can fetch the dumb-init and ProxySQL packages
RUN apt-get update && apt-get install -y wget

# Fetch the dumb-init package and install it
RUN wget ${dumb_init_base_url}/${dumb_init_package_name} \
    	 -O /tmp/${dumb_init_package_name} && \
    dpkg -i /tmp/${dumb_init_package_name} && \
    rm -f /tmp/${dumb_init_package_name}
    
# Fetch ProxySQL package and install it
RUN wget ${proxysql_base_url}/${proxysql_package_name} \
    	 -O /tmp/${proxysql_package_name} && \
    dpkg -i /tmp/${proxysql_package_name} && \
    rm -f /tmp/${proxysql_package_name}
# Cleanup
RUN rm -rf /var/lib/apt/lists/*

VOLUME /var/lib/proxysql

ENTRYPOINT ["/usr/bin/dumb-init", "--", "proxysql", "-f"]
