FROM solr:6

# Downloading config set from search_api_solr drupal module
RUN wget -qO- https://ftp.drupal.org/files/projects/search_api_solr-8.x-2.2.tar.gz \
        | tar xz -C /opt/docker-solr/scripts/ && \
    mkdir -p /opt/docker-solr/configsets/drupal && \
    mv "/opt/docker-solr/scripts/search_api_solr/solr-conf/6.x" /opt/docker-solr/configsets/drupal/conf && \
    rm -rf /opt/docker-solr/scripts/search_api_solr  && \
    mkdir /opt/solr/server/solr/drupal && \
    mkdir /opt/solr/server/solr/drupal/conf && \
    cp -R /opt/docker-solr/configsets/drupal/conf/* /opt/solr/server/solr/drupal/conf/ && \
    echo "name=drupal" > /opt/solr/server/solr/drupal/core.properties && \
    mkdir /opt/solr/server/solr/drupal/data
