#
# Aerospike Kubernetes Operator Init Container.
#

FROM ubuntu:18.04

# Install dependencies.
RUN apt-get update && apt-get install -y wget curl python3

# Download peer-finder.
RUN wget https://github.com/kmodules/peer-finder/releases/download/v1.0.0/peer-finder -O /usr/bin/peer-finder
RUN chmod +x /usr/bin/peer-finder

ADD entrypoint.sh /usr/bin/entrypoint.sh
RUN chmod +x /usr/bin/entrypoint.sh

RUN rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true
RUN apt-get clean

ENTRYPOINT ["/usr/bin/entrypoint.sh"]