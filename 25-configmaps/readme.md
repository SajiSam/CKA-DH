### Create a ConfigMap 
```bash
mkdir primary 
echo -n c > primary/cyan 
echo -n m > primary/magenta 
echo -n y > primary/yellow 
echo k > primary/black 
echo -n "known as key" >> primary/black 
echo -n blue > favorite 
```

```bash
kubectl create configmap colors  --from-literal=text=black  --from-file=./favorite  --from-file=./primary/ 
```

```bash
kubectl get configmap colors -o yaml 
```
