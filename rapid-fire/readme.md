### Switch Context 
```
kubectl config use-context docker-desktop
```

### Question 1
#### Create:

	Kind: Deployment
    Name: pod1
	Image: busybox:1.28
	Namespace: rapid-fire-cka
	Command: Sleep 1000
	Replicas: 2

### Question 2
#### Create:
	Kind: Pod
    Name: deploy2
	Image: redis
	Namespace: rapid-fire-cka

### Question 3
#### Scale down:
	Kind: Deployment
    Name: pod1
	Image: busybox:1.28
	Namespace: rapid-fire-cka
	Command: Sleep 1000
	Replicas: 1	<----
	Track changes: True

### Question 4
#### Replace:
	Kind: Pod
    Name: deploy2
	Image: nginx
	Namespace: rapid-fire-cka

### Question 5
#### Create:
	Kind: DaemonSet
    Name: fluentd-elasticsearch
	Image: gcr.io/fluentd-elasticsearch/fluentd:v2.5.1
	Namespace: kube-system
	volumes: 
		name: varlog 
			mountPath: /var/log
			hostPath:  /var/log  
		name: varlibdockercontainers 
			hostPath: /var/lib/docker/containers
			mountPath: /var/lib/docker/containers

### Question 6
#### Create:
	Kind: PersistentVolume
    Name: pv1
	Capacity: 1Gi
	AccessModes: ReadWriteMany
    HostPath: /tmp/pvc003

### Question 7
https://gitlab.platform-engineering.com/container-guild/cka/raw/master/pvs.yaml
#### Use Kubectl to get a list of:
	Kind: PersistentVolume
	Sort-By: Storage
	Columns: NAME,CAPACITY
	Headers: none

### Question 8
#### Update:
	Kind: Deployment
    Name: pod1
	Namespace: rapid-fire-cka
	image: redis

#### Undo last change:
	Kind: Deployment
    Name: pod1
	Namespace: rapid-fire-cka

### Question 9
#### Update:
	Kind: Deployment
    Name: pod1
	Namespace: rapid-fire-cka
	Replicas: 1
	Image: memcached

### Question 10
#### Create a service to Expose:
	Kind (to be exposed): Deployment
    Name: pod1
	Namespace: rapid-fire-cka
	Mode: NodePort
	Port: 11211
	Target-port: 11211

### Question 11
#### Print history:
	Kind: Deployment
    Name: pod1
	Namespace: rapid-fire-cka

### Question 12
#### Delete:
	Kind: everything
	Namespace: rapid-fire-cka

