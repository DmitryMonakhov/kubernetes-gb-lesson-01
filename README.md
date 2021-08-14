```sh
kubectl describe deployments -n kubedoom
```
```
Name:                   kubedoom
Namespace:              kubedoom
CreationTimestamp:      Sat, 14 Aug 2021 02:34:01 -0400
Labels:                 app=kubedoom
Annotations:            deployment.kubernetes.io/revision: 1
Selector:               app=kubedoom
Replicas:               1 desired | 1 updated | 1 total | 1 available | 0 unavailable
StrategyType:           RollingUpdate
MinReadySeconds:        0
RollingUpdateStrategy:  0 max unavailable, 1 max surge
Pod Template:
  Labels:           app=kubedoom
  Service Account:  kubedoom
  Containers:
   kubedoom:
    Image:        storaxdev/kubedoom:0.5.0
    Port:         5900/TCP
    Host Port:    5900/TCP
    Environment:  <none>
    Mounts:       <none>
  Volumes:        <none>
Conditions:
  Type           Status  Reason
  ----           ------  ------
  Available      True    MinimumReplicasAvailable
  Progressing    True    NewReplicaSetAvailable
OldReplicaSets:  <none>
NewReplicaSet:   kubedoom-57b69fdbc (1/1 replicas created)
Events:          <none>

```

```sh
kubectl describe po -n kubedoom
```
```
Name:         kubedoom-57b69fdbc-mkpnl
Namespace:    kubedoom
Priority:     0
Node:         kubernetes-gb-default-group-gb-0/10.0.0.8
Start Time:   Sat, 14 Aug 2021 04:31:35 -0400
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
    Container ID:   docker://888ccd8c814b618741ced8ce3690488c2c3720c84cf6f595bfe29006d1c45e32
    Image:          storaxdev/kubedoom:0.5.0
    Image ID:       docker-pullable://storaxdev/kubedoom@sha256:88dfe1b5430a678a8f399593fd9b2d256c86b29518a6924965fe1f1758da8cca
    Port:           5900/TCP
    Host Port:      5900/TCP
    State:          Running
      Started:      Sat, 14 Aug 2021 04:31:35 -0400
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
  Normal  Scheduled  12s   default-scheduler  Successfully assigned kubedoom/kubedoom-57b69fdbc-mkpnl to kubernetes-gb-default-group-gb-0
  Normal  Pulled     12s   kubelet            Container image "storaxdev/kubedoom:0.5.0" already present on machine
  Normal  Created    12s   kubelet            Created container kubedoom
  Normal  Started    12s   kubelet            Started container kubedoom
```
