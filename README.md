# Overview
This is a sample helm chart that can be used to deploy a cronjob.

## Job versus Cronjob
A Job creates one or more Pods and will continue to retry execution of the Pods until a specified number of them successfully terminate.  
A CronJob creates Jobs on a repeating schedule.

Note:  
If the job/cronjob is not reaching completion stage due to istio proxy - disabling sidecar injection is suggested. 
```
sidecar.istio.io/inject: "false"
```

### Ref:
https://kubernetes.io/docs/concepts/workloads/controllers/cron-jobs/  
https://kubernetes.io/docs/tasks/job/automated-tasks-with-cron-jobs/  

## Scaling Deployments using cronjob
```cronjob-for-scaling.yaml``` is a deployment resource which showcases how cronjob can be utilized to scale up and scale down deployments.  Please note additional Role and Rolebinding required for a new serviceaccount for scaling operations.
However this is not an ideal method to implement solely for cost saving methods. Horizontal pod autoscaling, Vertical Pod Autoscaling are two commonly recommended approaches. 
Google Kubernetes engine offer multi-dimensional Pod Autoscaling (Pre-GA at the time of writing). 
https://cloud.google.com/kubernetes-engine/docs/how-to/multidimensional-pod-autoscaling


