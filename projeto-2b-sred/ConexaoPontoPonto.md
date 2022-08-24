<h3>Etapa 2: Conexão Ponto a Ponto</h3>

- Nessa etapa, a princípio, deve-se criar uma rede ponto a ponto com 4 Máquinas Virtuais, via cabos Ethernet e switch. Podemos Desse modo, pode-se tomar, como exemplo, a conexão entre as díspares máquinas: ```VM01-PC04-PedroV```, ```VM02-PC04-PedroV```, ```VM01-PC03-PedroH``` e ```VM02-PC03-PedroH```.

- **Passo 1:** Fazer o login nas Máquinas Virtuais, caso ainda não estejam logadas. 

Ubuntu Login: ```administrador``` <br>
Password: ```adminifal```

- **Passo 2:** Editar o ```arquivo 01-netcfg.yaml```, verificando se ele está presente na pasta ```/etc/netplan/``` e realizar as configurações do endereçamento estático, com base na [Tabela de Configurações de cada Integrante](https://github.com/pedrohenriquee8/redes-grupo6-914/blob/main/projeto-2b-sred/Configuracoes.md#tabela-1-configurações-das-máquinas-virtuais-de-cada-integrante). Para isso, deve-se digitar o comando: ```$ sudo nano /etc/netplan/01-netcfg.yaml```.

  - Editar o campo ```addresses``` e inserir o IP definido pela equipe, sendo: ```192.168.14.88``` para ```VM01-PC04-PedroV``` e ```192.168.14.89``` para ```VM02-PC04-PedroV```;
  - Editar o campo ```gateway4``` e inserir o endereço definido pela equipe, sendo: ```192.168.14.81```;
  - Alterar o DHCP para o modo ```false```;
  - Salvar as alterações mediante as teclas CTRL + X;
  - Aplicar as mudanças realizadas por intermédio do comando ```$ sudo netplan apply```.
  
<p>Figura 1: Configurações do netplan do VM01-PC04-PedroV e do VM02-PC04-PedroV.</p>
<img src="" alt="Configurações do netplan do VM01-PC04-PedroV e do VM02-PC04-PedroV." title="Figura 1: Configurações do netplan do VM01-PC04-PedroV e do VM02-PC04-PedroV.">

- **Passo 3:** Realizar o mesmo processo para as Máquinas Virtuais ```VM01-PC03-PedroH``` e ```VM02-PC03-PedroH```.

  - Editar o campo ```addresses``` e inserir o IP definido pela equipe, sendo: ```192.168.14.85``` para ```VM01-PC04-PedroH``` e ```192.168.14.86``` para ```VM02-PC04-PedroH```;
  - Editar o campo ```gateway4``` e inserir o endereço definido pela equipe, sendo: ```192.168.14.81```;
  - Alterar o DHCP para o modo ```false```;
  - Salvar as alterações mediante as teclas CTRL + X;
  - Aplicar as mudanças realizadas por intermédio do comando ```$ sudo netplan apply```.

<p>Figura 2: Configurações do netplan do VM01-PC03-PedroH e do VM02-PC03-PedroH.</p>
<img src="" alt="Configurações do netplan do VM01-PC03-PedroH e do VM02-PC03-PedroH." title="Figura 2: Configurações do netplan do VM01-PC03-PedroH e do VM02-PC03-PedroH.">

- **Passo 4:**  Para finalizar os procedimentos de configuração, ´é de suma importância conectar os cabos Ethernet nos dois PCs e configurar a rede para **Modo Bridge** nas suas VMs. Segue abaixo a configuração: 

<p>Figura 3: Configurações de Rede no Modo Bridge.</p>
<img src="" alt="Configurações de Rede no Modo Bridge." title="Figura 3: Configurações de Rede no Modo Bridge.">

- **Aplicação:** 

Para concluir esta etapa com êxito, faz-se necessário digitar o comando ping entre as Máquinas Virtuais e verificar o envio e a recepção de pacotes. Assim sendo, tem-se como exemplo:

  - Ping da VM01-PC04-PedroV para VM02-PC03-PedroH <br>
    ```$ ping 192.168.14.86```
    
  - Ping da VM01-PC03-PedroH para VM02-PC04-PedroV <br>
    ```$ ping 192.168.14.88```



