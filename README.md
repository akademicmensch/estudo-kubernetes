# estudo-kubernetes

## Was ist das?

Escalabilidade vertical e escalabilidade horizontal.
Kubernetes entra na clusterização horizontal, mais especificamente na divisão de containers em diferentes máquinas (criação e gerenciamento de clusters, orquestrador de containers).


## study resume

Resources são features já criadas para que utilizemos o kubernetes de maneira mais eficaz.
Alguns exemplos: Pod, RS, Deploy, Volume, Persistence Volume, PVC SVC(balanceamento de carga), SC, DS, Quota.


Master: Control Planes: api, c-m, sched, etcd
Node: Ndes: kubelet e k-proxy



## kubectl e minikube

Kubectl -> Ferramenta necessária para se comunicar com a api do kubernetes. Ela nos dá as ações de criar, ler, atualizar e remover.
Minikube -> Ferramenta necessária para a criação de um cluster local. * Criar cluster: minikube start --vm-driver=virttualbox




## 1- Pods
Pod é uma capsula que pode conter 1 ou mais containers.

Criando o primeiro pod:
kubectl run nginx-pod --image=nginx:latest


Ver detalhes do pod criado: kubectl describe pod nginx-pod
Editar o pod: kubectl edit pod nginx-pod


Maneira declarativa de criar pods: escrevem-se arquivos de definições.
Arquivo: primeiro-pod.yaml. Executar: kubectl apply -f ./primeiro-pod.yaml

Deletar pod: kubectl delete pod nginx-pod ou kubectl delete -f ./primeiro-pod.yaml

Projeto mais elaborado: portal-noticias.yaml
 - Para entrar no portal-noticias pelo terminal: kubectl exec -it portal-noticias -- bash



## Expor Pods com services
- Como pods se comunicam com pods novos? Através do SVC(tem o clusterIp, NodePort e LoadBalancer).

1) ClusterIP (maneira de conseguir manter a comunicação com um pod mesmo que este caia e seja substituido por outro de IP diferente)
- Service de exemplo: svc-pod-2 e POD de exemplo pod-2

2) NodePort: Expor POD para mundo externo
Service de exemplo: svc-pod-1 e POD de exemplo pod-1


3) LoadBalancer - Abre comunicação para o mundo externo usando o load balancer do provedor
Service de exemplo: svc-pod-1-loadbalancer e POD de exemplo pod-1


Obs: arquivos no diretorio 'exemplificacao-SVC'



## 



## 



## 