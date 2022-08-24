<h3>Etapa 4: Acesso Remoto via SSH com HostOnly</h3>

- Na etapa 4, a princípio, devemos configurar o acesso remoto a todas as máquinas virtuais cadastradas, através do terminal do PC, por meio do SSH (Secure Socket Shell), que é um protocolo específico de segurança de troca de arquivos entre cliente e servidor utilizando a porta 22, sendo a única que precisa ficar aberta no firewall do servidor.

- **Passo 1:** Fazer o login nas Máquinas Virtuais, caso ainda não estejam logadas. 

Ubuntu Login: ```administrador``` <br>
Password: ```adminifal```

- **Passo 2:** Ativar a interface do computador para viabilizar o contato entre a VM e Host, que no caso é o PC.

  - No campo ```Arquivo``` na configuração da VM, deve-se acessar a opção ```Host Network Manager```;
  - Inserir manualmente os campos do Adaptador de acordo com a imagem abaixo:

<p>Figura 1: Acessando a opção Host Network Manager.</p>
<img src="" alt="Acessando a opção Host Network Manager." title="Figura 1: Acessando a opção Host Network Manager.">

  - Configurar o ```Servidor DHCP``` no adaptador VBoxNet0, devendo estar de acordo com a imagem abaixo:

<p>Figura 2: Verificando as configurações dos endereços na aba Servidor DHCP.</p>
<img src="" alt="Verificando as configurações dos endereços na aba Servidor DHCP." title="Figura 2: Verificando as configurações dos endereços na aba Servidor DHCP.">

  -  Verificar a configuração das interfaces usando o Terminal com o comando ```$ ifconfig -a```, observando a existência da interface ```vboxnet0```.

<p>Figura 3: Verificando a existência da interface vboxnet0.</p>
<img src="" alt="Verificando a existência da interface vboxnet0." title="Figura 3: Verificando a existência da interface vboxnet0.">

- **Passo 3:** Adicionar um adaptador ao HostOnly em uma VM.
  
  - Antes de iniciar, é de extrema importância dar acesso a uma VM via rede pelo Terminal do PC, sendo adicionado um novo Adaptador de rede à VM;
  - Acessar as configurações de Rede da VM desejada;
  - No Adaptador 2, deve-se habilitar a opção ```Habilitar Placa de Rede``` e selecionar no campo ```Conectado a```: ```Placa de rede exclusiva de hospedeiro (host-only)```, declarando o campo ```Nome``` como ```vboxnet0```.

- **Passo 4:** Ativar as configurações da interface na VM para o servidor DHCP.

  - Verificar a existência da interface ```enp0s8``` mediante o comando ```$ ifconfig -a```;
  - Feita a verificação, torna-se necessário acessar a configuração das interfaces no netplan. Assim sendo, deve-se digitar o comando ```$ sudo nano /etc/netplan/01-netcfg.yaml``` e ativar o DHCP para o Adaptador 2 (enp0s8), como demonstra a imagem abaixo:

<p>Figura 4: Acessando as configurações do netplan e ativando o DHCP para o Adaptador 2.</p>
<img src="" alt="Acessando as configurações do netplan e ativando o DHCP para o Adaptador 2." title="Figura 4: Acessando as configurações do netplan e ativando o DHCP para o Adaptador 2.">

  - Com isso, aplicam-se as alterações feitas mediante o uso do comando ```$ sudo netplan apply```;
  - Para verificar se a aplicação foi, de fato, implementada, utiliza-se o comando ```$ ifconfig -a```, como exibe a imagem abaixo:

<p>Figura 5: Verificando as configurações de interface do netplan.</p>
<img src="" alt="Verificando as configurações de interface do netplan." title="Figura 5: Verificando as configurações de interface do netplan.">

- **Aplicação:**
 
Sob essa perspectiva, a fim de concluir com êxito o acesso via SSH oriundo do Host-Only, é de suma importância que as Máquinas Virtuais estejam com as Configurações de Rede no **Modo Bridge**, outrossim, conectadas por intermédio de cabos Ethernet. Desse modo, segue um exemplo aplicado pela equipe, tendo o objetivo de exibir o processo da conexão realizada entre as máquinas.

 <p>Tabela 1: Orientação acerca da conexão a ser feita via SSH pelo Host-Only.</p>
 
|Orientação|
|----------|
|De: Host-Only|
|Para: VM01-PC03-PedroH|

Assim sendo, basta inserir, no terminal do servidor Host-Only (VM01-PC04-PedroV), o comando ```$ ssh administrador@192.168.14.85``` para realizar a conexão com êxito.

<p>Figura 6: Exemplo do uso do SSH oriundo do Host-Only.</p>
<img src="" alt="Exemplo do uso do SSH oriundo do Host-Only." title="Figura 6: Exemplo do uso do SSH oriundo do Host-Only.">
