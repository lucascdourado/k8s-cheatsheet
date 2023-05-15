# Kubernetes Cheatsheet
- [Kubernetes Cheatsheet](#kubernetes-cheatsheet)
  - [Creating Objects](#creating-objects)
  - [Monitoring Usage Commands](#monitoring-usage-commands)
  - [Node Commands](#node-commands)
  - [Pod Commands](#pod-commands)
  - [Deployment Commands](#deployment-commands)
  - [Service Commands](#service-commands)
  - [Endpoint Commands](#endpoint-commands)
  - [Ingress Commands](#ingress-commands)
  - [DaemonSet Commands](#daemonset-commands)
  - [StatefulSet Commands](#statefulset-commands)
  - [ConfigMap Commands](#configmap-commands)
  - [Secret Commands](#secret-commands)
  - [Rollout Commands](#rollout-commands)
  - [Job Commands](#job-commands)
  - [CronJob Commands](#cronjob-commands)
  - [Network Policy Commands](#network-policy-commands)



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

[⇡home](#kubernetes-cheatsheet)
## Monitoring Usage Commands

| Name | Command |  
| --- | --- |
| Get node cpu and memory utilization | `kubectl top node <node_name>` |
| Get pod cpu and memory utilization | `kubectl top pods <pod_name>` |

[⇡home](#kubernetes-cheatsheet)
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

[⇡home](#kubernetes-cheatsheet)
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

[⇡home](#kubernetes-cheatsheet)
## Deployment Commands

| Name | Command |
| --- | --- |
| Get deployment | `kubectl get deployment <deployment_name>` |
| Get deployment in yaml | `kubectl get deployment <deployment_name> -o yaml` |
| Get deployment wide information | `kubectl get deployment <deployment_name> -o wide` |
| Edit deployment | `kubectl edit deployment <deployment_name>` |
| Describe deployment | `kubectl describe deployment <deployment_name>` |
| Delete deployment | `kubectl delete deployment <deployment_name>` |
| Log deployment | `kubectl logs deployment/<deployment_name> -f` |
| Update image | `kubectl set image deployment <deployment_name> <container_name>=<new_image_name>` |
| Scale deployment with replicas | `kubectl scale deployment <deployment_name> --replicas=<replicas>` |

[⇡home](#kubernetes-cheatsheet)
## Service Commands

| Name | Command |
| --- | --- |
| Get service | `kubectl get service <service_name>` |
| Get service in yaml | `kubectl get service <service_name> -o yaml` |
| Get service wide information | `kubectl get service <service_name> -o wide` |
| Edit service | `kubectl edit service <service_name>` |
| Describe service | `kubectl describe service <service_name>` |
| Delete service | `kubectl delete service <service_name>` |

[⇡home](#kubernetes-cheatsheet)
## Endpoint Commands

| Name | Command |
| --- | --- |
| Get endpoint | `kubectl get endpoint <endpoint_name>` |

[⇡home](#kubernetes-cheatsheet)
## Ingress Commands

| Name | Command |
| --- | --- |
| Get ingress | `kubectl get ingress <ingress_name>` |
| Get ingress in yaml | `kubectl get ingress <ingress_name> -o yaml` |
| Get ingress wide information | `kubectl get ingress <ingress_name> -o wide` |
| Edit ingress | `kubectl edit ingress <ingress_name>` |
| Describe ingress | `kubectl describe ingress <ingress_name>` |
| Delete ingress | `kubectl delete ingress <ingress_name>` |

[⇡home](#kubernetes-cheatsheet)
## DaemonSet Commands

| Name | Command |
| --- | --- |
| Get daemonset | `kubectl get daemonset <daemonset_name>` |
| Get daemonset in yaml | `kubectl get daemonset <daemonset_name> -o yaml` |
| Edit daemonset | `kubectl edit daemonset <daemonset_name>` |
| Describe daemonset | `kubectl describe daemonset <daemonset_name>` |
| Delete daemonset | `kubectl delete daemonset <daemonset_name>` |

[⇡home](#kubernetes-cheatsheet)
## StatefulSet Commands

| Name | Command |
| --- | --- |
| Get statefulset | `kubectl get statefulset <statefulset_name>` |
| Get statefulset in yaml | `kubectl get statefulset <statefulset_name> -o yaml` |
| Edit statefulset | `kubectl edit statefulset <statefulset_name>` |
| Describe statefulset | `kubectl describe statefulset <statefulset_name>` |
| Delete statefulset | `kubectl delete statefulset <statefulset_name>` |

[⇡home](#kubernetes-cheatsheet)
## ConfigMap Commands

| Name | Command |
| --- | --- |
| Get configmap | `kubectl get configmap <configmap_name>` |
| Get configmap in yaml | `kubectl get configmap <configmap_name> -o yaml` |
| Edit configmap | `kubectl edit configmap <configmap_name>` |
| Describe configmap | `kubectl describe configmap <configmap_name>` |
| Delete configmap | `kubectl delete configmap <configmap_name>` |

[⇡home](#kubernetes-cheatsheet)
## Secret Commands

| Name | Command |
| --- | --- |
| Get secret | `kubectl get secret <secret_name>` |
| Get secret in yaml | `kubectl get secret <secret_name> -o yaml` |
| Edit secret | `kubectl edit secret <secret_name>` |
| Describe secret | `kubectl describe secret <secret_name>` |
| Delete secret | `kubectl delete secret <secret_name>` |

[⇡home](#kubernetes-cheatsheet)
## Rollout Commands

| Name | Command |
| --- | --- |
| Restart deployment | `kubectl rollout restart deployment <deployment_name>` |
| Undo deployment with last revision | `kubectl rollout undo deployment <deployment_name>` |
| Undo deployment with specific revision | `kubectl rollout undo deployment <deployment_name> --to-revision=<revision_number>` |
| Get all revisions of deployment | `kubectl rollout history deployment <deployment_name>` |
| Get specific revision of deployment | `kubectl rollout history deployment <deployment_name> --revision=<revision_number>` |

[⇡home](#kubernetes-cheatsheet)
## Job Commands
| Name | Command |
| --- | --- |
| Get job | `kubectl get job <job_name>` |
| Get job in yaml | `kubectl get job <job_name> -o yaml` |
| Edit jog in yaml | `kubectl edit job <job_name>` |
| Describe job | `kubectl describe job <job_name>` |
| Delete job | `kubectl delete job <job_name>` |

[⇡home](#kubernetes-cheatsheet)
## CronJob Commands
| Name | Command |
| --- | --- |
| Get cronjob | `kubectl get cronjob <cronjob_name>` |
| Get cronjob in yaml | `kubectl get cronjob <cronjob_name> -o yaml` |
| Edit cronjob | `kubectl edit cronjob <cronjob_name>` |
| Describe cronjob | `kubectl describe cronjob <cronjob_name>` |
| Delete cronjob | `kubectl delete cronjob <cronjob_name>` |

[⇡home](#kubernetes-cheatsheet)
## Network Policy Commands

| Name | Command |
| --- | --- |
| Get network policy | `kubectl get networkpolicy <networkpolicy_name>` |
| Get network policy in yaml | `kubectl get networkpolicy <networkpolicy_name> -o yaml` |
| Get network policy wide information | `kubectl get networkpolicy <networkpolicy_name> -o wide` |
| Edit network policy | `kubectl edit networkpolicy <networkpolicy_name>` |
| Describe network policy | `kubectl describe networkpolicy <networkpolicy_name>` |
| Delete network policy | `kubectl delete networkpolicy <networkpolicy_name>` |

[⇡home](#kubernetes-cheatsheet)
