# mlflow chart

Tested in `kind` on my local laptop. To test ingress in hosted kubernetes solution, we need to apply the correct `ingressClass` and annotations.

```sh
kubectl create ns mmm
helm upgrade --install mmm ./mlflow -f values.example.yaml --namespace mmm
```

2. How can you make sure this application does not go out of hand and consume all the cluster resources?

> by setting the resources constraints in the `values.yaml` file

3. How would you collect logs from this app for later analysis? Where and how would you save it?

> This is really a cost question. If budget allows, I would use datadog and collect all logs from the cluster globally: https://docs.datadoghq.com/containers/kubernetes/log/?tab=datadogoperator

> Another option I think is solid (never actually tried to work with) is Grafana's Loki: https://grafana.com/blog/2023/04/12/how-to-collect-and-query-kubernetes-logs-with-grafana-loki-grafana-and-grafana-agent/
