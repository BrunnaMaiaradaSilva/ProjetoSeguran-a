# Help

O Help é um app para segurança da mulher. 



### Pilares do Help

Etapa     |  Descrição |
--------- | -----------
Monitoramento | Armazenar e acompanhar, em tempo real, eventos que são gerados por todas as aplicações cadastradas
Triagem | Separar os eventos recebidos pelo Monitoramento de acordo com o tipo de ambiente, severidade e prioridade de cada um deles
Diagnóstico | Identificar possíveis falhas de desenvolvimento ou intermitências das aplicações conforme dados catalogados pela Triagem
Ação | Agir de acordo com a necessidade identificada pela etapa de Diagnóstico, acionando os recursos disponíveis para a solução dos problemas, além de definir e atualizar o status de cada evento
Manutenção | Propor resoluções para inconsistências e utilizar os dados de todas as etapas anteriores para sugerir melhorias e manutenções preventivas


#### Arquitetura do sistema

Decidimos separar as camadas de projeto, tendo como orientação o modelo Clean Architecture, de Bob Martin, mas usado aqui na visão de Steve Smith. Info: [Microsoft Docs](https://docs.microsoft.com/en-us/dotnet/architecture/modern-web-apps-azure/common-web-application-architectures).

Através desta modelo arquitetural, esperamos melhorar a forma como o projeto é separado e compreendido. Tendo também vantagens como uso de injeção de dependência, fazendo a inversão do controle e viabilizando testes automatizados (unitários a princípio).

Também nos serviu de base o material apresentado no livro Asp.NET Core Architecture e-book, disponível em [sítio Microsoft](https://dotnet.microsoft.com/download/e-book/aspnet/pdf).

#### Camada de Infraestrutura

São itens desta camada, aqueles relativos à:

* Conexão com banco de dados
* Tipos representando o banco de dados
* Implementações de acesso a dados (das Interfaces definidas no Core)

#### Camada de WebApi

Esta camada será responsável por receber as requisições dos clientes e endereçá-las.

Vamos tratar aqui:

* Autenticação e autorização
* Injeção de dependência


#### Camada de Data

* Criando migrations

Execute `dotnet ef migrations add "nome-da-migration" --project ./ItaLog/ItaLog.Data/ --startup-project ./ItaLog/ItaLog.API/` para gerar uma nova *migration* do banco de dados.

### Atualizando o banco de dados
Execute `dotnet ef database update --project ./ItaLog/ItaLog.Data/ --startup-project ./ItaLog/ItaLog.API/` atulizando o banco de banco de dados com as migrations do projeto.


#### Camada Domain

Esta camada é responsável por armazenar as abstrações do nosso universo. Por exemplo, o que é um log de erro será representado aqui por uma classe.

Nesta camada você vai encontrar os seguintes itens:

* Entidades
* Interfaces


## Ambiente de desenvolvimento

### Servidor de desenvolvimento
Execute `dotnet watch run --project ./ItaLog/ItaLog.Api/` para iniciar o servidor. Navegue em `http://localhost:5000/`. O aplicativo será recarregado automaticamente se você alterar qualquer um dos arquivos de origem.


### Build
Execute `dotnet build ./ItaLog/ItaLog.sln` para contruir os executaveis do projeto.


#### Camada Tests

Por fim uma camada para separar os testes será utilizada.

* Testes unitários
Execute `dotnet test ./ItaLog/ItaLog.sln` para iniciar os testes unitários via [xUnit](https://xunit.net/).

## Tecnologias utilizadas
* [.Net Core](https://dotnet.microsoft.com/download/dotnet-core/3.1) - versão 3.1.3
* [Entity Framework](https://docs.microsoft.com/pt-br/ef/) - versão 3.1.3
* [Auto Mapper](https://github.com/AutoMapper/AutoMapper) - versão 9.0.0
* [Identity](https://docs.microsoft.com/pt-br/aspnet/core/security/authentication/identity?view=aspnetcore-3.1&tabs=visual-studio) - versão 2.2.0
* [MailKit](https://github.com/jstedfast/MailKit) - versão 2.6.0
* [Moq](https://github.com/moq/moq4) - versão 4.14.1
* [xUnit](https://xunit.net/) - versão 2.4.1
* [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle) - versão 5.4.1

<!---->
<h3 id="devs"> Desenvolvedores </h3>

<table>
  <tr>
    	<th> <a href=></a> </th>
   	<th> <a href=></a> </th>
	<th> <a href="https://github.com/BrunnaMaiaradaSilva" target="_blank">
	<img src="https://avatars2.githubusercontent.com/u/45864414?s=460&u=31689f0d56c03fda7bf6052e37158c35bccc7cea&v=4" width="100" alt="Brunna Silva">
		</a>
	  </th>
	<th> <a href="https://github.com/Evanderjh">
		<img src="https://avatars2.githubusercontent.com/u/70240099?s=460&u=2fae1850645be7d2119434da5208a92bd7d45d6f&v=4" width="100" alt="Evander Pereira">
		</a>
	  </th>
    	<th> <a href=></a> </th>
	<th> <a href=></a> </th>
  </tr>
  <tr>
    <td><h4> Ester </h4></td>
    <td><h4> Danusa </h4></td>
	<td><h4> Brunna Silva </h4></td>
	<td><h4> Evander Pereira </h4></td>
    <td><h4> Felipe Dantas </h4></td>
    <td><h4> Kleberson </h4></td>
  </tr>  
</table>

