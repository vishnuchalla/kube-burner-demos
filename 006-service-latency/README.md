Run regular kube-burner cluster-density-v2 with:


``` shell
kube-burner-ocp cluster-density-v2 --iterations=216  --churn=false  --es-server=${ES_SERVER} --es-index=kube-burner-ocp
```

Examine indexed documents with `metricName: svcLatencyMeasurement`

