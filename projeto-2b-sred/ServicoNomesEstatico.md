<h3>Etapa 5: Serviço de Nomes Estático</h3>

- Na última etapa do projeto, observa-se a configuração dos nomes de host estático, sendo definidos localmente no diretório ```/etc/hosts```. Nesse sentido, para ter acesso aos recursos de host, o comando ```$ sudo nano /etc/hosts``` torna-se fundamental. 

- **Passo 1:** Digitar o comando ```$ sudo nano /etc/hosts``` no terminal da máquina.

- **Passo 2:** Ao acessar o diretório, cada integrante deve, em suas respectivas Máquinas Virtuais, digitar o endereço IP, o hostname, o domínio e o apelido de cada membro, tendo em vista a [Tabela de Configurações de cada Integrante](https://github.com/pedrohenriquee8/redes-grupo6-914/blob/main/projeto-2b-sred/Configuracoes.md#tabela-1-configurações-das-máquinas-virtuais-de-cada-integrante), obtendo como resultado a seguinte imagem:

<p>Figura 1: Acessando as configurações dos nomes de host estático.</p>
<img src="figuresProject/FifthStage/Dominios.png" alt="Acessando as configurações dos nomes de host estático." title="Figura 1: Acessando as configurações dos nomes de host estático.">

- **Passo 3:** Cada membro deve inserir, em cada Máquina Virtual, os usuários de todos os integrantes da equipe, possibilitando o uso do comando ```$ ssh <user>@<hostname|fqdn|alias>```. Para isso, basta utilizar o comando ```$ sudo adduser <NomeDoIntegrante>``` e adicionar as informações de cada membro.

- **Passo 4:** Digitar o comando ```sudo cat /etc/passwd``` a fim de verificar os usuários criados.

<p>Figura 2: Verificação da criação dos usuários.</p>
<img src="figuresProject/FifthStage/Users.png" alt="Verificação da criação dos usuários." title="Figura 2: Verificação da criação dos usuários.">

<p>Figura 3: Acessando os usuários criados na Máquina Virtual.</p>
<img src="figuresProject/FifthStage/AcessoUsers.png" alt="Acessando os usuários criados na Máquina Virtual." title="Figura 3: Acessando os usuários criados na Máquina Virtual.">

- **Passo 5:** Para concluir o projeto com êxito, faz-se necessário utilizar o ```comando ssh``` e acessar todas as Máquinas Virtuais, cada uma com a configuração de rede no modo Bridge, mediante o uso de cabos Ethernet conectados a um switch.

- **Aplicação:**

<p>Figura 4: Acessando a Máquina Virtual VM01-PC01-BiancaL via FQDN.</p>
<img src="figuresProject/FifthStage/SSHBianca1.png" alt="Acessando a Máquina Virtual VM01-PC01-BiancaL via FQDN." title="Figura 4: Acessando a Máquina Virtual VM01-PC01-BiancaL via FQDN.">

<p>Figura 5: Acessando a Máquina Virtual VM02-PC03-PedroH via FQDN.</p>
<img src="figuresProject/FifthStage/SSHPedroH2.png" alt="Acessando a Máquina Virtual VM02-PC03-PedroH via FQDN." title="Figura 5: Acessando a Máquina Virtual VM02-PC03-PedroH via FQDN">
