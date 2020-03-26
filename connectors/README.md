# Kafka Connect template for Kubernetes & OpenShift

## Place connector binaries in this directory

- To add a connector to your Kafka Connect environment, copy your connector JAR file(s) to the location specified in the `plugin.path` property of your Kafka Connect configuration (defined via `/config/connect-distributed.properties`).

- Connectors should be placed in the `/connectors` folder of this repository.

`cp <path_to_your_connector>.jar /connectors`
