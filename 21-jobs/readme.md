### Create a job which will run a busybox container which sleeps for three seconds then stops. 

Re-configure the job so that it has:

    backoffLimit = 3
    completions = 2
    parallelism = 2

Delete and re-deploy the job with above changes
