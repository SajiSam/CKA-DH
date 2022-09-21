# Create an API User with access to only read pods in your namespace

### Create namespace
`kubectl create ns << your surname >>`

### Create Service Account
`kubectl create sa << your forename >> -n << your surname >>`

### Create Role
`kubectl apply -f role.yaml`

### Create RoleBinding
`kubectl apply -f rolebinding.yaml`

### Extract Token from the Service Account
```
export NAMESPACE="<< your surname >>"
export K8S_USER="<< your forename >>"

RETRIEVING TOKEN:
kubectl -n ${NAMESPACE} describe secret $(kubectl -n ${NAMESPACE} get secret | (grep ${K8S_USER} || echo "$_") | awk '{print $1}') | grep token: | awk '{print $2}'\n

```

### Generate a KUBECONFIG file using the details above:
```
apiVersion: v1
clusters:
- cluster:
    certificate-authority-data: << copy from certificate-authority-data in ~/.kube/config >>
    server: https://10.140.0.10:6443 # Default for a kubeadm provisioned cluster
  name: mycluster

contexts:
- context:
    cluster: mycluster
    namespace: << your surname >>
    user: << your forename >>
  name: << your forename >>

current-context: << your forename >>
kind: Config
preferences: {}

users:
- name: << your forename >>
  user:
    token: # Output from "RETRIEVING TOKEN" script
```

### Use the KUBECONFIG
```
export KUBECONFIG=${path_to_config}
```

### Check Permissions
```
kubectl get nodes
Error from server (Forbidden): nodes is forbidden: User "system:serviceaccount:<< your surname >>:<< your forename >>" cannot list resource "nodes" in API group "" at the cluster scope
```

```
kubectl get pods
```

### List permissions for any user (as admin)
```
kubectl auth can-i --list --as=system:serviceaccount:<< your forename >>:<< your surname >>
```

### List permissions for your current user
```
kubectl auth can-i --list
```

#### Create a Pod/Deployment in the ${yoursurname} namespace
#### Create a Pod/Deployemnt in another namespace
#### Edit Role to allow the user to create and delete pods
