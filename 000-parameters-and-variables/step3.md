Run these commands

`/tmp/kube-burner init -c config.yml --uuid=demo`{{exec}}

List all created namespaces

```
kubectl get ns -l kube-burner-job=kube-burner-demo
kubectl get ns -l kube-burner-uuid=demo
```{{exec}}

List all deployments within a namespace

`kubectl get deploy -n kube-burner-demo-0`{{exec}}

List all deployments using label selector

`kubectl get deploy -A -l kube-burner-job=kube-burner-demo`{{exec}}

Manually destroy created stuff

`/tmp/kube-burner destroy --uuid=demo`{{exec}}

Set GC=true and re-run

`/tmp/kube-burner init -c config.yml`{{exec}}

Demonstrate that all namespaces were garbage collected at the end of the run

`kubectl get ns | grep kube-burner-demo`{{exec}}