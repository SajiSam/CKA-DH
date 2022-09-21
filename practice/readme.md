1. Deploy a **pod** named web in the namespace **cka1** using the image `nginx:1.16.0`

2. Deploy a **pod** with 2 busybox containers named busy-1 and busy-2 with a label `env=test` (the pod needs to run for at least 5 mins)

3. Create a **deployment** named cache from the image `memcached` with 3 replicas
 - Expose the deployment on a port on the host that sends to port 11211 of the pod.
 - Output the endpoints in json format to q3.json
 - Tracking changes; scale the deployment to 5 replicas
 - Output the history of this deployment to a file called q3.txt

4. Create a **file** called q4.yaml that defines a deployment in the **cka4** namespace, with six replicas running the `nginx:1.7.9` image.
 - Each pod should have the label `app=proxy`. 
 - The deployment should have the label `client=user`. 
 - Configure the deployment so that when the deployment is updated, the existing pods are killed off before new pods are created to replace them.

5. Deploy a redis **pod** named my-cache and use a busybox pod to lookup the IP address of redis outputting to q5.txt. *(this may error depending on DNS configuration of your cluster)*

6. Create a **deployment** with 5 replicas of nginx:latest. 
 - Expose the deployment internally with target-port 80 and port 8080
 - Add a label `app=website`
 - List the pods that make up this deployment, sorting by Pod IP and show the labels to a file q6a.txt
 - Repeat the list pods; this time only displaying columns Name & Status to a file q6b.txt

7. Convert the docker stack to kubernetes.