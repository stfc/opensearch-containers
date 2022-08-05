FROM docker.io/opensearchproject/opensearch-dashboards:1.3.4
USER 0

# usermod chowns the uid of files, but not the gid - we chown both later
# in one pass, so change the home dir here to prevent duplicated effort
RUN usermod -d /tmp/home/opensearch-dashboards opensearch-dashboards
RUN groupmod -g 4005 opensearch-dashboards
RUN usermod -u 4005 -g 4005 opensearch-dashboards
RUN usermod -d /usr/share/opensearch-dashboards opensearch-dashboards

RUN chown -R opensearch-dashboards:opensearch-dashboards /usr/share/opensearch-dashboards

USER 4005
