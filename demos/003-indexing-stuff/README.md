## Indexing metrics

Run these commands:

```shell
PROM_URL=$(echo https://$(oc get route -n openshift-monitoring prometheus-k8s -o jsonpath={.spec.host}))
TOKEN=$(oc sa new-token -n openshift-monitoring prometheus-k8s)
# Local indexing
kube-burner init -c config-local.yml -m metrics.yml -u ${PROM_URL} -t ${TOKEN}
# Elastic indexing
kube-burner init -c config-elastic.yml -m metrics.yml -u ${PROM_URL} -t ${TOKEN}
```

Use the index subcommand:

```shell
# Run with local indexing and browse thoughout some metric files
kube-burner index -m metrics.yml -u ${PROM_URL} -t ${TOKEN}
# Run with elastic indexing
kube-burner index -m metrics.yml -u ${PROM_URL} -t ${TOKEN} --es-server=${ES_SERVER} --es-index=kube-burner
```

[Grafana dashboard](https://grafana.rdu2.scalelab.redhat.com:3000/d/cf110eed-c1c7-4000-85a4-a86bd3162870/kube-burner-ask-ocp-admin-demo?from=1695116549608&to=1695120754412&var-Datasource=AWS+Dev+-+kube-burner&var-uuid=249da958-71e5-4efa-bc2c-8576308011e8&orgId=1)
