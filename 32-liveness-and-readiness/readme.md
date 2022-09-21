### Apply the following ConfigMap:
- [nginx default.conf](https://gitlab.platform-engineering.com/learnwithus/cka-training/-/blob/master/31-liveness-and-readiness/nginx-config.yaml)

### Create an deployment of two nginx pods and add:
- A tcpSocket readiness probe:
   - Port: 8000
   - initialDelaySeconds: 5
   - period: 10
- A httpGet liveness probe:
   - Port: 80
   - Path: /healtz
   - failureThreshold: 1
   - initialDelaySeconds: 30
   - period: 10

### Fix the readiness probe in the running deployment

### Fix the liveness probe in the running deployment 
