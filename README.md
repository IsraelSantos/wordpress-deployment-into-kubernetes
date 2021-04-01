### exercicioskubernetes
Repositório para estudos sobre Kubernets

## Teste com minikube do exercício DeployWordpress

# Para testar com minikube basta executar os seguintes comandos

Iniciar o minikube

`$ minikube start`

Efetuar o deployment

`$ kubectl apply -k ./`

Criar acesso externo à porta 80 para teste

`$ kubectl port-forward svc/wordpress 8000:80`

Vizualizar o ip para acesso de teste

`$ minikube service wordpress --url`

Visualizar os pods e services

`$ kubectl get pods,services`

Para limpar tudo no final basta executar

`$ kubectl delete -k ./`
`$ minikube stop`
