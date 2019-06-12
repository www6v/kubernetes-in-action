# Kubernetes in action

This repository contains all the code (and some additional files) from my [Kubernetes in Action](https://www.manning.com/books/kubernetes-in-action) book.

# Tested
Chapter04  
1. kubia-replicaset.yaml  
2. ssd-monitor-daemonset.yaml
```
kubectl get ds（daemonset）
```

Chapter05  
1. kubia-svc.yaml   一个服务一个端口  
2. kubia-svc-named-ports.yaml    一个服务多个端口  
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

```
[root@10-25-3-55 Chapter05]# curl -6 -g  "172.17.243.253:80"
You've hit kubia-cjrqd
```
3. kubia-svc-loadbalancer.yaml
```
[root@10-25-3-55 Chapter05]# kubectl get  svc kubia-loadbalancer
NAME                 TYPE           CLUSTER-IP      EXTERNAL-IP       PORT(S)        AGE
kubia-loadbalancer   LoadBalancer   172.17.207.29   120.132.105.235   80:45823/TCP   88s
```

```
[root@10-25-3-55 Chapter05]# curl http://120.132.105.235
You've hit kubia-nx4rs
```




