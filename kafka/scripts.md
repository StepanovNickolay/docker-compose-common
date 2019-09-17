# Basic kafka scripts

### Create topic 
kafka-topics.sh --create --bootstrap-server $1 --replication-factor 1 --partitions 1 --topic $2

### Console consumer
kafka-console-consumer --bootstrap-server $1 --from-beginning --topic $2

### Console producer
kafka-console-producer --broker-list $1 --topic n$2

### Clean topic
kafka-topics --zookeeper $1 --alter --topic $2 --config retention.ms=1000

kafka-configs --zookeeper $1 --entity-type topics --alter --entity-name $2 --add-config retention.ms=1000

kafka-configs --zookeeper $1 --entity-type topics --alter --entity-name $2 --delete-config retention.ms
