# Rundeck Community Helm Chart

O Rundeck permite que você transforme seus procedimentos operacionais em trabalhos de autoatendimento. Dê com segurança a outras pessoas o controle e a visibilidade de que precisam. Saiba mais sobre o Rundeck em https://www.rundeck.com/open-source.


## Instalação

    git clone https://github.com/JackExperts/helm-charts.git

    cd charts/rundeck

    helm install nome_do_release -n nome_do_namespace .

## Configuração

As seguintes configurações podem ser ajustadas. Recomenda-se usar o values.yaml para sobrescrever a configuração do Rundeck.


Parâmetro | Descrição | Padrão
--------- | ----------- | -------
deployment.replicaCount | Quantas réplicas executar. O Rundeck geralmente só funciona com uma. | 1
deployment.annotations | Você pode passar anotações dentro de deployment.spec.template.metadata.annotations. Útil para KIAM/Kube2IAM e outros, por exemplo.	 | {}
deployment.strategy | Define a estratégia de rollout do Kubernetes para o deployment do Rundeck.	 | { type: RollingUpdate }
image.repository | Nome da imagem a ser executada, sem a tag.	 | [rundeck/rundeck](https://github.com/rundeck/rundeck)
image.tag | A tag da imagem a ser usada. | 4.17.0
image.pullPolicy | A política de pull da imagem no Kubernetes. | IfNotPresent
image.pullSecrets | O segredo do Kubernetes para puxar a imagem de um registro privado. | None
service.type | O tipo de serviço Kubernetes a ser usado. | ClusterIP
service.port | A porta TCP na qual o serviço deve ouvir. | 80
ingress | Regras de ingress a serem aplicadas.	 | None
resources | Restrições de recursos a serem aplicadas.	| None
rundeck.adminUser | A configuração para configurar o usuário administrador que deve ser colocado no arquivo realm.properties.	 | "admin:admin,user,admin,architect,deploy,build"
rundeck.env | As variáveis de ambiente do Rundeck que você gostaria de definir. | Variáveis padrão fornecidas no arquivo docker |
rundeck.envSecret | Nome do segredo contendo variáveis de ambiente a serem adicionadas ao deployment do Rundeck. | ""
rundeck.sshSecrets | Uma referência ao Segredo do Kubernetes que contém as chaves SSH. | ""
rundeck.awsConfigSecret | Nome do segredo para montar no diretório ~/.aws/. Útil quando o AWS IRSA não é uma opção. | ""
rundeck.kubeConfigSecret | Nome do segredo para montar no diretório ~/.kube/. Útil quando o Rundeck precisa de configuração para vários clusters K8s.	| ""
rundeck.extraConfigSecret | Nome do segredo contendo arquivos adicionais a serem montados em ~/extra/. Pode ser útil ao trabalhar com a configuração RUNDECK_TOKENS_FILE.	| ""
nginxConfOverride | Um valor opcional de várias linhas que pode substituir o nginx.conf padrão.	 | ""
persistence.enabled |Se deve ou não anexar armazenamento persistente ao pod do Rundeck.	| false
persistence.claim.create | Se o gráfico Helm deve criar uma solicitação de volume persistente. Consulte o values.yaml para mais opções de solicitação. | false
persistence.awsVolumeId | Um ID de Volume de uma volume AWS EBS preexistente para persistir os dados do Rundeck no caminho /home/rundeck/server/data.	| None
persistence.existingClaim | Nome de uma solicitação de volume existente.
serviceAccount.create | Defina como verdadeiro para criar uma conta de serviço para o pod do Rundeck.	 | false
serviceAccount.annotations | Um mapa de anotações para associar à conta de serviço (por exemplo, AWS IRSA).	 | {}
serviceAccount.name | Nome da conta de serviço que o pod do Rundeck deve usar. | ""
volumes | Volumes disponíveis para todos os contêineres. | ""
volumeMounts | VolumeMounts a serem adicionados ao contêiner do Rundeck. | ""
initContainers | Podem ser usados para baixar plugins ou personalizar a instalação do Rundeck. | ""
sideCars | Podem ser usados para executar contêineres adicionais no pod. | ""




