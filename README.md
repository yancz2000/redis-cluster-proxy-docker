# redis-cluster-proxy-docker
Run redis cluster proxy in docker.

### Useage:  
Port (default: 7777)  
redis-cluster-proxy [OPTIONS] [node1_host:node1_port,node2_host:node2_port,...]
  
### Examples:  
docker run -id --name redis-cluster-proxy-test redis-cluster-proxy 10.222.38.166:6379 10.222.33.161:6379 10.222.10.130:6379  
docker run -id --name redis-cluster-proxy-test -v /redis-cluster-proxy/proxy.conf:/proxy.conf redis-cluster-proxy "-c" "/proxy.conf"  
docker run -id --name redis-cluster-proxy-test -p 17777:7777 redis-cluster-proxy 10.222.38.166:6379 10.222.33.161:6379 10.222.10.130:6379  

### Connect:  
redis-cli -h container_ip -p 7777  
redis-cli -h host_ip -p 17777
