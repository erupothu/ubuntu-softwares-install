
#### steps to install


wget https://dlcdn.apache.org/kafka/3.2.0/kafka_2.13-3.2.0.tgz  
tar xzf kafka_2.13-3.2.0.tgz  
sudo mv kafka_2.13-3.2.0 /usr/local/kafka  

sudo nano /etc/systemd/system/zookeeper.service  

```sh
[Unit]
Description=Apache Zookeeper server
Documentation=http://zookeeper.apache.org
Requires=network.target remote-fs.target
After=network.target remote-fs.target

[Service]
Type=simple
ExecStart=/usr/local/kafka/bin/zookeeper-server-start.sh /usr/local/kafka/config/zookeeper.properties
ExecStop=/usr/local/kafka/bin/zookeeper-server-stop.sh
Restart=on-abnormal

[Install]
WantedBy=multi-user.target
```

sudo nano /etc/systemd/system/kafka.service  

```sh
[Unit]
Description=Apache Kafka Server
Documentation=http://kafka.apache.org/documentation.html
Requires=zookeeper.service

[Service]
Type=simple
Environment="JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64"
ExecStart=/usr/local/kafka/bin/kafka-server-start.sh /usr/local/kafka/config/server.properties
ExecStop=/usr/local/kafka/bin/kafka-server-stop.sh

[Install]
WantedBy=multi-user.target
```

sudo systemctl daemon-reload  
sudo systemctl start zookeeper  
sudo systemctl start kafka  

cd /usr/local/kafka  
bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic testTopic  
bin/kafka-topics.sh --list --bootstrap-server localhost:9092  


bin/kafka-console-producer.sh --broker-list localhost:9092 --topic testTopic  
bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic testTopic --from-beginning  

