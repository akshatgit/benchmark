# OpenMessaging Benchmark Framework

Important commands:
- Run Benchmark:
```bash
node0:~/benchmark$: bin/benchmark  --drivers driver-kafka/kafka-latency.yaml   workloads/simple-workload.yaml
```
- Create a kafka topic
```bash
node0:~/kafka$: bin/kafka-topics.sh --create --bootstrap-server 10.10.1.1:9092 --replication-factor 5 --partitions 10 --topic test3
```
- Produce to a kafka topic
```bash
node0:~/kafka$: bin/kafka-console-producer.sh --broker-list 10.10.1.1:9092  --topic test3 --request-required-acks 1 
```
- Consume from a kafka topic:
```bash
node0:~/kafka$: bin/kafka-console-consumer.sh --bootstrap-server 10.10.1.1:9092 --topic test3 --from-beginning
```
- Set heap space for kafka:
```bash
node0:~/kafka$: export KAFKA_HEAP_OPTS='-Xmx128G -Xms128G'
```
- Get under-replicated-partitions:
```bash
node0:~/kafka$: bin/kafka-topics.sh  --bootstrap-server 10.10.1.1:9092 --describe --under-replicated-partitions
```
