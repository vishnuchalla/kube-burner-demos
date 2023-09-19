## Running kube-burner

Run these commands

```shell
kube-burner init -c config.yml --uuid=demo

# Listein all created namespaces
oc get ns | grep ask-ocp-admin
# Listing all deployments within a namespace
oc get deploy -n ask-ocp-admin-4
# Listing all deployments using a label selector
oc get deploy -n ask-ocp-admin -l kube-burner-job=ask-ocp-admin

# Manually destroy created stuff
kube-burner destroy --uuid=demo

# Set gc to true and re-run
kube-burner init -c config.yml
```

Demonstrate that all namespaces were garbage collected at the end of the run

```shell
oc get ns | grep ask-ocp-admin
```
