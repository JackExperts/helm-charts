# MaaS Helm Chart

TODO: Descrição e objetivo

## Instalação

    git clone https://github.com/JackExperts/helm-charts.git
    helm install charts/maas

## Configuração

TODO: Como configurar

Parámetro | Descrição | Valor padrão
--------- | ----------- | -------
zabbix.enabled | Helm Chart do Zabbix | true
timescaledb-single.enabled | Helm Chart do TimescaleDB  | true
grafana.enabled | Helm Chart do Grafana | true
rundeck.enabled | Helm Chart do Rundeck  | [rundeck/rundeck](https://github.com/rundeck/rundeck)
alertaio.enabled | Helm Chart do AlertaIO | [rundeck/rundeck](https://github.com/rundeck/rundeck)

## TODO

- Parametrizar de forma padrão o TimescaleDB
  - Hook (POS) para criar database, user e password para o Zabbix;
  - Hook (POS) para subir dados iniciais da database do Zabbix, assim como rodar script timescaledb.sql
- Parametrizar de forma padrão o Zabbix
- Parametrizar de forma padrão o Grafana
  - Hook (PRE) para criar usuário no Zabbix para entregar ao Grafana o usuário e senha com acesso a API
- Parametrizar de forma padrão o Rundeck
- Parametrizar de forma padrão o OpenLDAP
- Parametrizar de forma padrão o AlertaIO

