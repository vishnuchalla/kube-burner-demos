## OCP Wrapper

Enumerate the available workloads and explain what value adds this wrapper to default kube-burner's.

Run node-density with local-indexing

```shell
kube-burner-ocp node-density --local-indexing --pods-per-node=150
```

Run cluster-density:

```shell
kube-burner-ocp cluster-density-v2 --es-server=${ES_SERVER} --es-index=kube-burner --iterations=30 --churn=false
```
