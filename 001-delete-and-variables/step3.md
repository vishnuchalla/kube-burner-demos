Explain how functions from [sprig](http://masterminds.github.io/sprig/) can be called, [working example](templates/secret.yml)

```plain
/tmp/kube-burner init -c config.yml --uuid=demo
```{{exec}}

Demonstrate that only deployments have been deleted in the namespace
```plain
kubectl get deploy,secret -n create-stuff
```{{exec}}