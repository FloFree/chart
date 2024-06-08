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
