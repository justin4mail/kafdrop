ref : 
    https://tecadmin.net/how-to-install-apache-kafka-on-ubuntu-20-04/


Commands: 

    start:
        sudo systemctl start zookeeper
        sudo systemctl start kafka
        sudo systemctl status kafka

    Create Topic:
        cd /usr/local/kafka
        bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic testTopic
        
    list all topics
        bin/kafka-topics.sh --list --zookeeper localhost:2181


Send/Recieve msgs:

    Send:
        cd /usr/local/kafka
        bin/kafka-console-producer.sh --broker-list localhost:9092 --topic testTopic

    Receive: 
        cd /usr/local/kafka
        bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic testTopic --from-beginning

