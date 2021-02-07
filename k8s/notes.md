# K8s Notes

## Namespaces: organise objects in a cluster

Generally used adding the following flag to any `kubectl` command `--namespace=<namespace name>`

## Viewing Objects
* `kubectl get <resource type>` - lists all resources of that type (in a given namespace)
* `kubectl get <resource type> <obj name>` - get information for a specific resource
* `kubectl describe <resource type> <obj name>` - detailed information for resource

## Creating/Updating Objects
* `kubectl apply -f <yml file>` - apply the changes (ex create/update resources) to reach declared state in yml
* `kubectl delete -f <yml file>` - delete the resources declared in a yml
* `kubectl delete <resource type> <obj name>` - delete a particular resource

## Interacting w/ Running Pods
* `kubectl logs <pod name>` - show logs of a particular running pod
* `kubectl exec -it <pod name>` - create a shell inside a pod
* `kubectl attach -t <pd name>` - attack to running process in pod
* `kubectl cp <pod name>:</path/to/pod/files> </path/to/local/file>` - copy a file from the pod to local machine
* `kubectl port-forward <pod name> 8080:80` - forwards traffic from local port 8080 to remote container port 80

## Monitoring Nodes/Pods on a cluser
* `kubectl top nodes` - display total cpu/memory in use by nodes
* `kubectl top opods` - dispaly all pods and resource usage
