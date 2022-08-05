FROM docker.io/opensearchproject/opensearch:1.3.4
USER 0

# usermod chowns the uid of files, but not the gid - we chown both later
# in one pass, so change the home dir here to prevent duplicated effort
RUN usermod -d /tmp/home/opensearch opensearch
RUN groupmod -g 4005 opensearch
RUN usermod -u 4005 -g 4005 opensearch
RUN usermod -d /usr/share/opensearch opensearch

RUN chown -R opensearch:opensearch /usr/share/opensearch

USER 4005
