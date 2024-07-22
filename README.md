
kafka-acls --bootstrap-server localhost:9092 --add --allow-principal User:kafkaclient1 --operation read --topic dat  --command-config admin.properties

kafka-acls --bootstrap-server localhost:9092 --add --deny-principal 'User:*' --operation Read --topic '*'  --command-config admin.properties

docker run --rm --tty confluentinc/cp-kafkacat kafkacat -b 192.168.1.8:9092 -L -X security.protocol=SASL_PLAINTEXT  -X sasl.mechanisms=PLAIN  -X sasl.username=admin -X sasl.password=admin-secret