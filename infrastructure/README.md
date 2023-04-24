# 애니시아 기반
- Nomad
  - 애니시아: Nomad
  - 가리사니: Kubernetes

# Network
```
docker network create --subnet=10.0.0.0/8 anissia
```

# Consul
```
docker run -d --net anissia -p 8500:8500 -p 8600:8600 --ip 10.10.10.1 --name=consul consul
```

# Elasticsearch
```
# 램용량이 무한정 늘어나는 문제가 있어서 2기가에서 락을 걸었다.
docker run -d --name elasticsearch -p 9200:9200 --net anissia -p 9300:9300 -m 2g --restart=always -e "xpack.security.enabled=false" -e "discovery.type=single-node"  docker.elastic.co/elasticsearch/elasticsearch:8.7.0
```
