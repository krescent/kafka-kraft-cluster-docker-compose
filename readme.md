docker run -it --rm --network kafka-kraft-cluster-docker-compose_kafka-net confluentinc/cp-kafka /bin/kafka-console-producer --bootstrap-server kafka01:9092 --topic test_topic
docker run -it --rm --network kafka-kraft-cluster-docker-compose_kafka-net confluentinc/cp-kafka /bin/kafka-producer-perf-test --topic test --num-records 1000000 --throughput -1 --producer-props bootstrap.servers=kafka01:9092 batch.size=16384 acks=1 linger.ms=50 --record-size 1000