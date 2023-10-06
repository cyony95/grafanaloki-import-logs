# grafanaloki-import-logs
A simple web app that takes CSVs of logs exported from Grafana(with Loki as a datasource) and importing them back into Loki using fluentd.
The architecture contains 2 containers in the same pod using a shared volume to exchange data. One container has python + Flask to serve a simple website and make the transformation from one CSV(as Grafana exports it) to multiple json (one per log message). The other container has fluentd configured to read from the shared volume and send the logs to Grafana to be viewed.
Helm chart and Dockerfiles provided.
