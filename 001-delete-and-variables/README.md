## Delete jobs and variables

Explain how a delete job works and how labelSelector, apiVersion and kind need to be configured

Show how variables work within kube-burner templates

```yaml
inputVars:
  foo: bar
```

Explain how functions from [sprig](http://masterminds.github.io/sprig/) can be called

```shell
kube-burner init -c config.yml
# Demonstrate that all resources have been deleted in the namespace
oc get pod,secret -n create-stuff
```
