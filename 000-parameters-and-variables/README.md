## Running kube-burner

Relevant variables:

- name: Job name
- namespace: Namespace prefix or name
- jobIterations: Number of job iterations
- qps/burst: API rate
- namespacedIterations: Each job iteration creates a new namespace
- waitWhenFinished: When enabled, kube-burner waits for all pods/builds to be running/complete before finishing the job
- preLoadImages: Pre load all container images in the nodes

Run these commands

```shell
kube-burner init -c config.yml --uuid=demo

# Listing all created namespaces
oc get ns -l kube-burner-job=kube-burner-demo
oc get ns -l kube-burner-uuid=demo
# Listing all deployments within a namespace
oc get deploy -n kube-burner-demo-4
# Listing all deployments using a label selector
oc get deploy -A -l kube-burner-job=kube-burner-demo

# Manually destroy created stuff
kube-burner destroy --uuid=demo

# Set gc to true and re-run
kube-burner init -c config.yml
```

Demonstrate that all namespaces were garbage collected at the end of the run

```shell
oc get ns | grep kube-burner-demo
```
