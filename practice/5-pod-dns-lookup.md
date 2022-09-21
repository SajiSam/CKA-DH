```kubectl run --generator=run-pod/v1 my-cache --image=redis

kubectl expose pod my-cache --port 11211

kubectl run --generator=run-pod/v1 looker-upper --image busybox:1.27 sleep 10000

kubectl exec -it looker-upper nslookup my-cache

kubectl get po -o wide

kubectl exec -it looker-upper nslookup 10-1-3-88.default.pod.cluster.local```
