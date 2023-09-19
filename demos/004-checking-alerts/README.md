## Alerting

Run a prometheus instance

```shell
podman run --rm -d --name prometheus --network=host docker.io/prom/prometheus:latest
```

Use simple alert-profile and check-alerts with it

```shell
$ cat up.yml 
- expr: up == 1
  description: Prometheus {{$labels.instance}} is up & running
  severity: info
```

```shell
kube-burner check-alerts -a up.yml -u http://localhost:9090
```

On an OCP cluster run these commands

```shell
PROM_URL=$(echo https://$(oc get route -n openshift-monitoring prometheus-k8s -o jsonpath={.spec.host}))
TOKEN=$(oc sa new-token -n openshift-monitoring prometheus-k8s)
kube-burner check-alerts -a alerts.yml -u ${PROM_URL} -t ${TOKEN}
```
