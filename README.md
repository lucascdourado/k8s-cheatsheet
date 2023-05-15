# Kubernetes Cheatsheet

- [Kubernetes Cheatsheet](#kubernetes-cheatsheet)
  - [Creating Objects](#creating-objects)
  - [Monitoring Usage Commands](#monitoring-usage-commands)
  - [Node Commands](#node-commands)
  - [Pod Commands](#pod-commands)
  - [Deployment Commands](#deployment-commands)


## Creating Objects
| Name | Command |
| --- | --- |
| Create resource | `kubectl apply -f ./<file_name>.yaml `| 
| Create from multiple files | `kubectl apply -f ./<file_name1>.yaml -f ./<file_name2>.yaml` |
| Create all files in directory | `kubectl apply -f ./<directory_name>` |
| Create from url | `kubectl apply -f https://<url>` |
| Create pod | `kubectl run <pod_name> --image <image_name>` |
| Create pod, then expose it as service | `kubectl run <pod_name> --image <image_name> --port <port> --expose` |
| Create pod yaml file | `kubectl run <pod_name> --image image_name --dryrun=client -o yaml > <file_name>.yaml` |
| Create deployment | `kubectl create deployment <deployment_name> --image <image_name>` |
| Create deployment yaml file | `kubectl create deployment <deployment_name> --image <image_name> --dryrun=client -o yaml > <file_name>.yaml` |
| Create deployment | `kubectl create deployment <deployment_name> --image <image_name>` |
| Create deployment yaml file | `kubectl create deployment <deployment_name> --image <image_name> --dryrun=client -o yaml > <file_name>.yaml` |
| Create service | `kubectl create service <service-type> <service_name> --tcp=<port:target_port>` |
| Create service yaml file | `kubectl create service <service-type> <service_name> --tcp=<port:target_port> --dryrun=client -o yaml > <file_name>.yaml` |
| Expose service from pod/deployment | `kubectl expose deployment <pod/deployment_name> --type=<service-type> --port <port> --target-port <target_port>` |
| Create config map from key-value | `kubectl create configmap <configmap_name> --from-literal=<key>:<value> --from-literal=<key>:<value>` |
| Create config map from file | `kubectl create configmap <configmap_name> --from-file=<file_name>` |
| Create config map from env file | `kubectl create configmap <configmap_name> --from-env-file=<file_name>` |
| Create secret from keyvalue | `kubectl create secret generic <secret_name> --from-literal=<key>:<value> --from-literal=<key>:<value>` |
| Create secret from file | `kubectl create secret generic <secret_name> --from-file=<file_name>` |
| Create job | `kubectl create job <job_name> --image <image_name>` |
| Create job from cronjob | `kubectl create job <job_name> --from=cronjob/<cronjob_name>` |
| Create cronjob | `kubectl create cronjob --image=<image_name> --schedule='<cron-syntax>' -- <command> <args>` |

[home ⤴](#kubernetes-cheatsheet)

## Monitoring Usage Commands

| Name | Command |  
| --- | --- |
| Get node cpu and memory utilization | `kubectl top node <node_name>` |
| Get pod cpu and memory utilization | `kubectl top pods <pod_name>` |

[home ⤴](#kubernetes-cheatsheet)
## Node Commands

| Name | Command |
| --- | --- |
| Describe node | `kubectl describe node <node_name>` |
| Get node in yaml | `kubectl get node <node_name> -o yaml` |
| Get node  | `kubectl get node <node_name>` |
| Drain node | `kubectl drain node <node_name>` |
| Cordon node | `kubectl cordon node <node_name>` |
| Uncordon node | `kubectl uncordon node <node_name>` |
| Delete node | `kubectl delete node <node_name>` |

[home ⤴](#kubernetes-cheatsheet)
## Pod Commands

| Name | Command |
| --- | --- |
| Get pod | `kubectl get pod <pod_name>` |
| Get pod in yaml | `kubectl get pod <pod_name> -o yaml` |
| Get pod in wide format | `kubectl get pod <pod_name> -o wide` |
| Get pod with watch | `kubectl get pod <pod_name> -w` |
| Edit pod | `kubectl edit pod <pod_name>` |
| Describe pod | `kubectl describe pod <pod_name>` |
| Delete pod | `kubectl delete pod <pod_name>` |
| Log pod | `kubectl logs pod <pod_name>` |
| Tail -f pod | `kubectl logs pod -f <pod_name>` |
| Exec pod | `kubectl exec -it <pod_name> -- <command>` |

[home ⤴](#kubernetes-cheatsheet)
## Deployment Commands