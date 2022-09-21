### Create a deployment using the image vish/stress

#### Assign resources as:

    limits = memory: "500Mi"
    requests= memory: "100Mi"

#### Pass args to the container in the pod:
    args:
    - -cpus
    - "2"
    - -mem-total
    - "550Mi"
    - -mem-alloc-size
    - "100Mi"
    - -mem-alloc-sleep
    - "1s"

### Replace the deployment with the new spec. What happens?
