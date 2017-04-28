# Sending your docker logs
Sending logs securely via syslog tls docker containers to Logit.io

## How to run

```sh
docker run -d \
  --name="logit" \
  --volume=/var/run/docker.sock:/var/run/docker.sock \
  logit/logitio-docker:latest \
  syslog+tls://<LOGSTASH-ENDPOINT>:<SYSLOG-TLS-PORT>
```

This container will gather logs from other containers that are started without the -t option and are configured with a logging driver that works with docker logs (journald and json-file).

This container is built on top of logspout: https://github.com/gliderlabs/logspout
