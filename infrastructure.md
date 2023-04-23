# 애니시아 기반
- Nomad
  - 애니시아: Nomad
  - 가리사니: Kubernetes

# 도커 네트워트
```
docker network create --subnet=10.0.0.0/8 anissia
```

# consul
```
docker run -d -p 8500:8500 -p 8600:8600 --net anissia --ip 10.10.10.1 --name=consul consul
```

