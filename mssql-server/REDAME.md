# Instalando o MS-SQL Server 2017 no Devuan

### 1. Instroduçao

### 2. Instalando um conatiner do MSSQL-SERVER
Execute o docker em seu computador com os seguintes parametros:
```bash
sudo docker run --name mssqlserver -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=@MyMSSQLDocker112' -p 1433:1433 -d microsoft/mssql-server-linux
```
Onde,
-–name mssqlserver -> representa o nome do container;
-e ‘ACCEPT_EULA=Y’ -e ‘SA_PASSWORD=@MyMSSQLDocker112′ -> representa o uso de variáveis de ambiente que configuram a senha do banco e aceite dos termos de uso;
-p 1433:1433 -> representa a liberação da porta 1433 do SQL Server;
-d microsoft/mssql-server-linux -> representa o uso da imagem oficial do MS SQL Server;

### 3. Listando o container do MSSQL-SERVER Instalado
Liste o container onde esta rodando o seu servdior
```bash
sudo docker ps
```

### 4. Acessando o MSSQL-SERVER via docker

```bash
sudo docker exec -it mssqlserver /opt/mssql-tools/bin/sqlcmd -S localhost -U sa -P @MyMSSQLDocker112
```
Onde,
docker exec -> executa outro processo num container ativo;
-it -> solicita interação (i) e uso do terminal (t);
mssqlserver -> nome do container criado;
/opt/mssql-tools/bin/sqlcmd -> binário do client seguido de seus parâmetros -S e -U e -P;

### 4. Referencia Bibliografica
[SQL SERVER em qualquer distribuicao Linux usando docker](https://www.linuxdescomplicado.com.br/2017/06/saiba-como-instalar-o-microsoft-sql-server-2017-em-qualquer-distribuicao-linux-usando-container-docker.html)
