```sh
kubectl get deployments -n kubedoom -owide
```
```
NAME       READY   UP-TO-DATE   AVAILABLE   AGE   CONTAINERS   IMAGES                     SELECTOR
kubedoom   1/1     1            1           63m   kubedoom     storaxdev/kubedoom:0.5.0   app=kubedoom
```

```sh
kubectl describe po -n kubedoom
```
```
Name:         kubedoom-57b69fdbc-2nhlc
Namespace:    kubedoom
Priority:     0
Node:         kubernetes-gb-default-group-gb-0/10.0.0.8
Start Time:   Sat, 14 Aug 2021 02:34:01 -0400
Labels:       app=kubedoom
              pod-template-hash=57b69fdbc
Annotations:  <none>
Status:       Running
IP:           10.0.0.8
IPs:
  IP:           10.0.0.8
Controlled By:  ReplicaSet/kubedoom-57b69fdbc
Containers:
  kubedoom:
    Container ID:   docker://644d125a80739dac674305d6b7ce08b168fac8179aa3fff0896978b898fa2062
    Image:          storaxdev/kubedoom:0.5.0
    Image ID:       docker-pullable://storaxdev/kubedoom@sha256:88dfe1b5430a678a8f399593fd9b2d256c86b29518a6924965fe1f1758da8cca
    Port:           5900/TCP
    Host Port:      5900/TCP
    State:          Running
      Started:      Sat, 14 Aug 2021 02:34:18 -0400
    Ready:          True
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kubedoom-token-s7rmv (ro)
Conditions:
  Type              Status
  Initialized       True
  Ready             True
  ContainersReady   True
  PodScheduled      True
Volumes:
  kubedoom-token-s7rmv:
    Type:        Secret (a volume populated by a Secret)
    SecretName:  kubedoom-token-s7rmv
    Optional:    false
QoS Class:       BestEffort
Node-Selectors:  <none>
Tolerations:     node.kubernetes.io/not-ready:NoExecute op=Exists for 300s
                 node.kubernetes.io/unreachable:NoExecute op=Exists for 300s
Events:
  Type    Reason     Age   From               Message
  ----    ------     ----  ----               -------
  Normal  Scheduled  57m   default-scheduler  Successfully assigned kubedoom/kubedoom-57b69fdbc-2nhlc to kubernetes-gb-default-group-gb-0
  Normal  Pulling    57m   kubelet            Pulling image "storaxdev/kubedoom:0.5.0"
  Normal  Pulled     57m   kubelet            Successfully pulled image "storaxdev/kubedoom:0.5.0" in 16.05769983s
  Normal  Created    57m   kubelet            Created container kubedoom
  Normal  Started    57m   kubelet            Started container kubedoom
```
