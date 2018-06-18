# Docker ELK Stack

1. Set env variables

    ```shell
    LOCALHOST="127.0.0.1"
    ```

1. Pull all resources

    ```shell
    docker pull docker.elastic.co/elasticsearch/elasticsearch:6.2.3 & \
    docker pull docker.elastic.co/logstash/logstash:6.2.3 & \
    docker pull docker.elastic.co/kibana/kibana:6.2.3 & \
    docker pull docker.elastic.co/beats/packetbeat:6.2.3 & \
    docker pull docker.elastic.co/beats/metricbeat:6.2.3 &  
    ```

1. Start Logstash container

    ```shell
    docker run -d \
      --name logstash \
      -it \
      -v /var/docker/vol/logstash/logstash-6.2.3/config:/usr/share/logstash/config \
      -p 0.0.0.0:9600:9600 \
      docker.elastic.co/logstash/logstash:6.2.3
    ```

1. Start Elasticsearch container
