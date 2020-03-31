# Kafka Connect template for Kubernetes & OpenShift

## Usage
1. Clone this repository to your local machine.

2. Add connector binaries to `/connectors`

3. Build & push the container image
  - **Example:** `docker build -t kafkaconnect:0.0.1 .`

4. Determine any new connector-specific configuration properties files which are needed to be available at runtime.

5. Add any new connector-specific properties files into the `chart/kafka-connect-template/config` directory and parameterize any desired sensitive information. Update `values.yaml` accordingly to reflect the new parameterization of the properties file.

6. If required, download the EventStreams Truststore file (e.g. `es-cert.jks`) and place it in the `chart/kafka-connect-template/config` directory.

7. Generate a templated set of kubernetes YAMLs from the Helm Chart, including the necessary values via `--set` flags or a provided `values.yaml` file.
   - **Example:** `helm template --output-dir templates --validate kc-s3 chart/kafka-connect-template`

8. Apply generated Kubernetes YAMLs
  - **Example:** `kubectl apply -f templates/kafka-connect-template/templates`

9. Start connectors
  - Details TBD
  - Start an installed connector using the Kafka Connect REST API by providing the configuration JSON file for your chosen connector.
    `curl -X POST http://localhost:8083/connectors -H "Content-Type: application/json" -d @<config>.json`
  - You will need to start each connector individually.
  - View the status of a connector using the Kafka Connect REST API.
    `curl http://localhost:8083/connectors/<connector_name>/status` **TO BE UPDATED**
