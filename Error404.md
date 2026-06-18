Matérial de estudo retirado do github do professor marcioclay

Algumas observações é necessária quando estiver manipulando/criando docker no seu linux.
Ao executar o comando
```
sudo containerlab deploy -t lab-ebpf.clab.yml --reconfigure
```
A resposta do linux não me parecia correta.
O retorno foi que os IPs do Node -A e Node -B era 172.20.20.3 e 172.20.20.2. Achei que isso poderia ser algum erro de configuração, arquivo corrompido.
Ao pesquisar e conversar com o professor, isso é um retorno normal utilizando o Docker.
Para saber se tudo está funcionando é necessário utilizar o Ping para saber 

```
sudo docker exec -it clab-ebpf-node-a ping 10.0.0.2
```
Esse ping é relacionado ao número do ip já pre definido da minha máquina Node B




Eu enfrentei um Erro ao executar o comando 
```
clab deploy -t topologia.yml
```

Containers ["clab-ebpf-lab-node-a" "clab-ebpf-lab-node-b"] already exist.   

  Add '--reconfigure' flag to the deploy command to first remove the          

  containers and then deploy the lab. 

Ao mostrar isso e relatar todo o procedimento ao Gemini, a resposta foi que durante os experimentos anteriores, ocorreu uma 
"preconfiguração" e quando eu tentava executar esse comando "clab deploy -t topologia.yml", o erro me alertava que ja existia.

```
sudo clab deploy -t topologia.yml --reconfigure
```
Depois desse comando ele fará uma reconfiguração.
