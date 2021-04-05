### exercicioskubernetes
Repositório para estudos sobre Kubernets

## Teste com minikube do exercício DeployWordpress

# Para testar com minikube basta executar os seguintes comandos

Iniciar o minikube

`$ minikube start`

Efetuar o deployment (esse comando também pode ser usado para deployment na sua núvem caso tenha configurado acesso a um cluster remoto AKS ou EKS ou similares)

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

Para testar o auto scaling basta executar o seguinte comando e observar o comportamento na tela administrativa do Kubernetes

`$ kubectl run -i --tty load-generator --rm --image=busybox --restart=Never -- /bin/sh -c "while sleep 0.01; do wget -q -O- http://wordpress; done"`
