# kafka-local

Tooling to get started with kafka development fast.

`$ docker-compose up`

## Kafka HQ

[http://localhost:10002/local/topic](http://localhost:10002/local/topic)

[https://tchiotludo.github.io/kafkahq/](https://tchiotludo.github.io/kafkahq/)

- Cluster State
- View Topics / Partitions
- Consume messages per topic
- ??? Produce messages per topic ???

Configuration: `kafkahq.yml`

```yaml
kafkahq:
  key: local-dev
  connections:
    local:
      properties:
        bootstrap.servers: 'docker.for.mac.localhost:9092'
      schema-registry:
        url: 'http://docker.for.mac.localhost:8081' # (optional)
```

## KafDrop

[http://localhost:10001/](http://localhost:10001/)

[https://github.com/obsidiandynamics/kafdrop](https://github.com/obsidiandynamics/kafdrop)

- Cluster State
- View Topics / Partitions
- Consume messages per partition

Configuration: `docker-compose.yml`

```yaml
kafdrop:
  image: obsidiandynamics/kafdrop
  environment:
    KAFKA_BROKERCONNECT: docker.for.mac.localhost:9092
    SCHEMAREGISTRY_CONNECT: 'http://docker.for.mac.localhost:8081'
```

## Kadmin

[http://localhost:10000/kadmin](http://localhost:10000/kadmin)

[https://github.com/bettercloud/kadmin](https://github.com/bettercloud/kadmin)

- Consume messages per topic
- Produce messages per topic

Configuration: `kadmin.properties`

```conf
kafka.host=docker.for.mac.localhost:9092
schema.registry.url=http://docker.for.mac.localhost:8081
```
