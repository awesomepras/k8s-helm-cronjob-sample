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

