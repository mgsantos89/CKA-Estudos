# Fortio

O Fortio é uma ferramenta de teste de carga e benchmarking projetada especificamente para aplicativos Kubernetes. Ele permite simular cargas de tráfego em serviços Kubernetes para avaliar o desempenho e a escalabilidade. O Fortio é útil para identificar gargalos, otimizar recursos e garantir que os aplicativos funcionem conforme o esperado em diferentes condições 

Exemplo de Uso:
```
kubectl run -it fortio --rm --image=fortio/fortio -- load -qps 800 -t 120s -c 70 "http://goserver-service/healthz"
``````

Sobre o comando

```kubectl run```: É o comando para executar um contêiner em um cluster Kubernetes.

```-it fortio```: Especifica o nome do recurso (nesse caso, o nome do pod) como "fortio".


```--rm```: Isso solicita que o contêiner seja removido após a conclusão do teste.


```--image=fortio/fortio```: Especifica a imagem Docker a ser usada para o contêiner, que é "fortio/fortio". Esta imagem contém o Fortio, a ferramenta de teste de carga que será usada.


```-- load```: Esta parte do comando é passada diretamente para o contêiner que está sendo executado, indicando que o Fortio deve ser usado para realizar um teste de carga.


```-qps 800```: Especifica a taxa de solicitações por segundo (800 solicitações por segundo).


```-t 120s```: Define o tempo de execução do teste como 120 segundos (2 minutos).


```-c 70```: Especifica o número de conexões concorrentes (70 conexões).


```"http://goserver-service/healthz"```: É a URL do serviço que será testada. O Fortio irá gerar cargas de solicitações para este URL para avaliar o desempenho do serviço. Neste caso, parece ser um serviço chamado "goserver-service" com um endpoint "/healthz".