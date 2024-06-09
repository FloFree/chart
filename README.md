# chart

Il repository viene utilizzato per gestire la pubblicazione di nuovi chart

Per fare questo:

- si aggiornano i Chart.yaml e values.yaml nella cartella

- si crea un nuovo pacchetto e si aggiorna il file index

```
helm package base-dep ./base-dep
helm repo index .
```

Fatto questo ed eseguito la commit/push il nuovo pacchetto viene esposto e reso disponibile.

Per verificare la pubblicazione:

```
helm repo add flofree-chart https://flofree.github.io/chart/
helm repo update
helm search repo flofree-chart --versions

helm pull flofree-chart/base-dep --untar
helm install base-dep ./base-dep
helm list
kubectl get service
kubectl port-forward service/base-dep 8080:8080
helm uninstall base-dep
```
