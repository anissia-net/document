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
docker run -d -p 8500:8500 -p 8600:8600 --net anissia --ip 10.10.10.1 --name=consul consul
```

# Elasticsearch
```
docker run --name elasticsearch -p 9200:9200 --net anissia -p 9300:9300 --restart=always -e "xpack.security.enabled=false" -e "discovery.type=single-node"  docker.elastic.co/elasticsearch/elasticsearch:8.7.0
```
