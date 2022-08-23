<h3>Etapa 3: Acesso Remoto via SSH</h3>

- Dando continuidade às práticas anteriores, o principal objetivo dessa etapa é configurar o acesso remoto via SSH nos servidores, sendo:

<p>Tabela 1: Nome dos discentes e a declaração dos seus respectivos servidores.</p>

|Discente|Servidores|
|--------|-----------------|
|Bianca Laiany|VM01-PC01-BiancaL<br>VM02-PC01-BiancaL|
|Pedro Henrique|VM01-PC03-PedroH<br>VM02-PC03-PedroH|
|Pedro Vinícius|VM01-PC04-PedroV<br>VM02-PC04-PedroV|
|Thayná Ingrid|VM01-PC02-Thayna<br>VM02-PC02-Thayna|

- **Passo 1:** Fazer o login nas Máquinas Virtuais, caso ainda não estejam logadas. 

Ubuntu Login: ```administrador``` <br>
Password: ```adminifal```

- **Passo 2:** Logo em seguida, é fundamental atribuir aos nomes servidores hostname. Nesse sentido, coloca-se o seguinte comando ```$ sudo hostnamectl set-hostname <hostname>``` em cada uma das VMs.

<p>Tabela 2: Declaração dos hostnames de cada integrante.</p>

|Discente|Descrição|Hostnames|
|-------|---------|---------|
|Bianca Laiany|VM01-PC01-BiancaL<br>VM02-PC01-BiancaL|bianca1<br>bianca2|
|Pedro Henrique|VM01-PC03-PedroH<br>VM02-PC03-PedroH|pedroh1<br>pedroh2|
|Pedro Vinícius|VM01-PC04-PedroV<br>VM02-PC04-PedroV|pedrov1<br>pedrov2|
|Thayná Ingrid|VM01-PC02-Thayna<br>VM02-PC02-Thayna|thayna1<br>thayna2|

Nesse sentido, foi preciso colocar os comandos com base nas respectivas máquinas, por exemplo: ```$ sudo hostnamectl set-hostname bianca01``` para a VM01-PC01-BiancaL.
