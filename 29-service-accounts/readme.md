#### 1.Create a service account ‘pod-admin’
`kubectl create sa pod-admin`
#### 2.Create a nginx:1.7.9 pod that uses this service account.
`kubectl run sa-pod --image=nginx:1.7.9 -o yaml --dry-run`
add `serviceAccountName: pod-admin` under `spec`

#### 3.Create a deployment of redis with 2 replicas.
`kubectl create deploy redis --image=redis`
`kubectl scale deploy redis --replicas=2`

#### 1.Update the deployment so the the pods use the service account.
`kubectl edit deploy redis` add `serviceAccountName: pod-admin` under `spec`
