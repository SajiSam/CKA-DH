### Create a new namespace called low-usage-limit 
### Create a YAML file which limits CPU and memory usage. The kind to use is LimitRange.

	default: cpu = 1 & memory = 500Mi 
	defaultRequest: cpu= 0.5 &  memory: 100Mi 
    type: Container 
	namespace: low-usage-limit

#### Apply the YAML file and Verify the LimitRange has been created

#### Create a deployment called limited-hog using image vish/stress in the low-usage-limit namespace

#### Describe the pod and view the limits
