FROM envoyproxy/envoy:latest

COPY envoy.yml /etc/envoy/envoy.yaml

CMD /usr/local/bin/envoy -c /etc/envoy/envoy.yaml --log-path /dev/stdout
