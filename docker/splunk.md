# Docker splunk

1. Pull all resources

    ```
    docker pull splunk/splunk
    ```

1. Run splunk

    ```shell
    docker run -d \
    --name=splunk-enterprise \
    --restart=always \
    -e "SPLUNK_START_ARGS=--accept-license" \
    -e "SPLUNK_USER=root" \
    -p "0.0.0.0:8000:8000" \
    splunk/splunk
    ```

    or

    ```shell
    docker run -d \
    --name splunk-enterprise \
    --hostname splunk-enterprise \
    --restart=always \
    -e "SPLUNK_START_ARGS=--accept-license" \
    -e "SPLUNK_USER=splunk" \
    -p "0.0.0.0:8000:8000" \
    -v /opt/splunk/etc:/opt/splunk/etc \
    -v /opt/splunk/var:/opt/splunk/var \
    splunk/splunk:7.0.0
    ```


1. Check that it's working

    ```
    curl
    ```
