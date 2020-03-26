# Kafka Connect template for Kubernetes & OpenShift

## Usage
1. Add connector binaries to `/connectors`

2. Build & push the container image
  - **Example:** `docker build -t kafkaconnect:0.0.1 .`

3. Update `connector.yaml`
  - Details TBD

4. Apply `connector.yaml`
  - **Example:** `kubectl apply -f connector.yaml`

5. Start connectors
  - Details TBD
  - Start an installed connector using the Kafka Connect REST API by providing the configuration JSON file for your chosen connector.
    `curl -X POST http://localhost:8083/connectors -H "Content-Type: application/json" -d @<config>.json`
  - You will need to start each connector individually.
  - View the status of a connector using the Kafka Connect REST API.
    `curl http://localhost:8083/connectors/<connector_name>/status` **TO BE UPDATED**
