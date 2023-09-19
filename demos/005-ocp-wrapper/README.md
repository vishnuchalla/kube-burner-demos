## OCP Wrapper

Enumerate the available workloads and explain what value adds this wrapper to default kube-burner's entrypoint

Run node-density

```shell
kube-burner ocp node-density --es-server=${ES_SERVER} --pods-per-node=150
```

[OCP Wrapper report](https://grafana.rdu2.scalelab.redhat.com:3000/d/9qdKt3K4z/kube-burner-report-ocp-wrapper?orgId=1&var-Datasource=AWS+Dev+-+kube-burner&var-platform=AWS&var-sdn=OpenShiftSDN&var-workload=node-density&var-nodes=5&var-uuid=4cc2dd74-da11-4f4b-b4d4-62acb3ddf18f&var-master=ip-10-0-133-30.us-west-2.compute.internal&var-master=ip-10-0-173-62.us-west-2.compute.internal&var-master=ip-10-0-217-162.us-west-2.compute.internal&var-worker=ip-10-0-133-30.us-west-2.compute.internal&var-worker=ip-10-0-134-24.us-west-2.compute.internal&var-worker=ip-10-0-138-96.us-west-2.compute.internal&var-worker=ip-10-0-173-62.us-west-2.compute.internal&var-worker=ip-10-0-217-162.us-west-2.compute.internal&var-infra=&var-latencyPercentile=P99&from=1695122340496&to=1695124402064)