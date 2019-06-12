# Kubernetes in action

This repository contains all the code (and some additional files) from my [Kubernetes in Action](https://www.manning.com/books/kubernetes-in-action) book.

# 测试过的
Chapter04  
kubia-replicaset.yaml  
ssd-monitor-daemonset.yaml  
kubectl get ds（daemonset）

Chapter05  
kubia-svc.yaml   一个服务一个端口  
kubia-svc-named-ports.yaml    一个服务多个端口  
```
[root@10-25-3-55 Chapter05]# kubectl describe svc kubia
Name:              kubia
Namespace:         default
Labels:            <none>
Annotations:       <none>
Selector:          app=kubia
Type:              ClusterIP
IP:                172.17.243.253
Port:              http  80/TCP
TargetPort:        8080/TCP
Endpoints:         10.25.246.245:8080,10.25.30.233:8080,10.25.62.9:8080
Port:              https  443/TCP
TargetPort:        8443/TCP
Endpoints:         10.25.246.245:8443,10.25.30.233:8443,10.25.62.9:8443
Session Affinity:  None
Events:            <none>

```





