

#### steps for installation

curl -fsSL https://packages.redis.io/gpg | sudo gpg --dearmor -o /usr/share/keyrings/redis-archive-keyring.gpg  
echo "deb [signed-by=/usr/share/keyrings/redis-archive-keyring.gpg] https://packages.redis.io/deb $(lsb_release -cs) main" | sudo tee   /etc/apt/sources.list.d/redis.list  
sudo apt-get update  
sudo apt-get install -y redis-server  
systemctl enable redis-server  

nano /etc/redis/redis.conf
```
bind 0.0.0.0
requirepass "<YOUR_PASSWORD>"
masterauth "<YOUR_PASSWORD>"
```

slave config
nano /etc/redis/redis.conf
```
bind 0.0.0.0
requirepass "<YOUR_PASSWORD>"
masterauth "<YOUR_PASSWORD>"
replicaof <MASTER_NODE_IP> 6379
```

service redis-server restart  
tail -f /var/log/redis/redis-server.log  

#### Sentinel for monitoring master and slave redis-servers  
sudo apt install redis-sentinel  
systemctl enable redis-sentinel  

nano /etc/redis/sentinel.conf  
```
sentinel monitor mymaster <MASTER_NODE_IP> 6379 2
sentinel auth-pass mymaster <YOUR_PASSWORD>
sentinel down-after-milliseconds mymaster 5000
sentinel failover-timeout mymaster 60000
protected-mode no
```

sudo service redis-sentinel restart  
tail -f /var/log/redis/redis-sentinel.log  
redis-cli -p 26379  

