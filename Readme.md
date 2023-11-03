
# Kafka, Kafka-connect, ElasticSearch (ES sink Connector)

Created a bread & butter functionality for starting seamless kafka services in no time.




## Docker Service

```bash
  kafka-es-kafkaconnect.yaml
```

Run this docker compose file with command:

```bash
  docker compose -f kafka-es-kafkaconnect.yaml up -d
```


## Services and Ports

| Service | Port     | 
| :-------- | :------- | 
| `elasticsearch` | `9200` |
| `zookeeper` | `2181` |
| `kafka` | `9092` |
| `schema-registry` | `8081` |
| `kafka-connect` | `8083` |
| `schema-registry-ui` | `8001` |
| `kafka-connect-ui` | `8086` |




## Installation of ES sink

Install ES sink connector using https://www.confluent.io/hub/confluentinc/kafka-connect-elasticsearch

#### Using confluent hub command
```bash
  #start Kafka connect in executable mode
  confluent-hub install confluentinc/ kafka-connect-elasticsearch:14.0.10
```
#### Restart Kafka connect service. It can be verified using:
* Kafka connect UI running on http://localhost:8086/
* ```bash
  curl -s localhost:8083/connector-plugins

## ES Sink Config

Sample connector added at ```connectors/es.kafka.json```.
Add this along with ES mapping. 


## Testing

* Admin Kafka - https://kafka.js.org/docs/admin
* Producer - https://kafka.js.org/docs/producing
* Consumer - https://kafka.js.org/docs/consuming (Test along with ES by using same TOPIC )