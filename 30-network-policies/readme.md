### 1.Create a memcached pod called my-db. 
`kubectl run my-db --image=memcached`

#### 1a.Add the label `app=database`
`kubectl label pod my-db app=database`

### 2.Create a nginx pod called my-proxy.
`kubectl run my-proxy --image=nginx`
#### 2a. Add the label `app=proxy`
`kubectl label pod my-proxy app=proxy`

### 3.Create 2x Network Security Policies called `allow-database` and `allow-proxy` that allow Egress and Ingress to those pods:
```
To the memcached pod on port 11211 ONLY from pods that have the label database-access=true 
To the nginx pod on port 80 ONLY from pods that have the label proxy-access=true
```

### 4.Create a redis pod called my-cache and ensure it cannot access either access either my-db and my-proxy pods.
#### 4a.Update the pod to allow it to access those pods.
