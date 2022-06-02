# Pinpoint

Pinpoint is an application monitoring platform.

## Add Repository for Dependency
Add helm repository for dependency (Stable,Incubator,Gradiant).
```
> helm repo add gradiant https://gradiant.github.io/charts
> helm repo add incubator https://charts.helm.sh/incubator 
> helm repo add stable https://charts.helm.sh/stable
```

## Deploy Pinpoint
```
> helm dependency update pinpoint
> helm install [Release Name] pinpoint -n [Namespace]
```

## Comandos úteis

Pré-requisito:
```
> export KUBECONFIG=<arquivo de kubeconfig do cluster>
```

Listando release do pinpoint
```
> helm list -n pinpoint
```

Listando histório da release
```
> helm history -n pinpoint pinpoint
```

Buscando informações de implementação
```
> helm get values -n pinpoint pinpoint 
## utilize --revision para ver de um momento específico
```

Para atualizar a release
```
> helm upgrade -n pinpoint pinpoint <dir do chart>
```

Para validar sintax
```
> helm lint <dir do chart>
```