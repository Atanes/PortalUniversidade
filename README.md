# PortalUniversidade
Portal da Universidade - Exemplo utilizado em Aulas de programação Web para turmas de Sistemas de Informação e Engenharia da Computação

## Objetivo
Mostrar a aplicação do JSF (Java Server Face) junto com o Hibernate para criar um portal WEB que permite o cadastro, listagem e pesquisa 
de professores 🧑‍🏫, campus da Universidade 🏫 e estudantes 👩‍🎓, entre outras coisas.

### Tecnologias/Ferramentas Utilizadas
Java, JSF, PostGreSQL / MYSQL, Hibernate, Netbeans 8

### Execução do projeto

No Netbeans, clicar no menu EQUIPE (TEAM em Inglês) e depois em GIT/Clonar, adicionar a 
url ```https://github.com/Atanes/PortalUniversidade.git``` no campo "URL do Repósitório", 
deixar usuario e senha em branco, depois é só clicar em próximo/next até o final do processo; 

Fazer o download do arquivo [jandex-2.0.3.final.jar](https://mvnrepository.com/artifact/org.jboss/jandex/2.0.3.Final)
e depois colocá-lo na pasta: ```C:\Program Files\NetBeans 8.0.2\java\modules\ext\hibernate4```

Nas propriedades do projeto, procurar as bibliotecas do hibernate, clicar em editar, procurar a classe Jandex
no diretorio ```C:\Program Files\NetBeans 8.0.2\java\modules\ext\hibernate4``` e adicionar no projeto.

Trocar a classe de conexao do PostgreSQL pela do Banco de Dados que você estiver usando (Oracle, por exemplo!)

Alterar o arquivo persistence.xml para:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<persistence version="2.0" xmlns="http://java.sun.com/xml/ns/persistence" 
                           xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                           xsi:schemaLocation="http://java.sun.com/xml/ns/persistence 
                           http://java.sun.com/xml/ns/persistence/persistence_2_0.xsd">
  <persistence-unit name="ProfessorPU">
    <provider>org.hibernate.ejb.HibernatePersistence</provider>
    <properties>
            <property name="javax.persistence.jdbc.url"
                      value="URL DO BANCO QUE VOCE ESTIVER USANDO" />
                        (Exemplo para o banco Oracle da Univeridade: "jdbc:oracle:thin:@(DESCRIPTION=(ADDRESS_LIST=(ADDRESS=(PROTOCOL=TCP)(HOST=10.20.250.13)(PORT=1521)))(CONNECT_DATA=(SERVICE_NAME=DBFACET)))")
            <property name="javax.persistence.jdbc.user"
                      value="USUARIO PARA ACESSO AO BANCO" />
            <property name="javax.persistence.jdbc.password"
                      value="SENHA PARA ACESSO AO BANCO" />
            <property name="javax.persistence.jdbc.driver"
                      value="DRIVER DO BANCO QUE VOCE ESTIVER USANDO" />
                        (Exemplo para o banco Oracle: "oracle.jdbc.OracleDriver")
            <property name="hibernate.dialect"
                      value="DIALETO DO BANCO QUE VOCE ESTIVER USANDO"/>
                        (Exemplo para o banco Oracle: "org.hibernate.dialect.Oracle9Dialect")
            <property name="hibernate.hbm2ddl.auto"
                      value="update" />
            <property name="hibernate.show_sql" value="true" />
            <property name="hibernate.format_sql" value="true" />          
        </properties>
  </persistence-unit>
</persistence>
```
Clicar sobre o projeto com o botão direito do mouse e depois selecionar "Limpar e Construir";

Executar o projeto.

### Observação importante 
A partir dos anos 2018 as aplicações Web começaram a seguir um padrão diferente com a separação em camadas (front-end e back-end) para
poder atender uma demanda crescente de novas exigencias técnicas e permitir um desenvolvimento mais rápido e organizado, como isso algumas
tecnologias como o Java Server Faces perderam sua maior qualidade que era a integração direta como os códigos Java para a criação de páginas
WEB dinamicas e com isso deixaram de ser tão populares na comunidade de desenvolvimento.

Por esse motivo não realizei mais nenhuma atualização nesse código e deixo os amantes do JSF a vontade para utilizar esse código como ponto
de partida para seu "divertimento" programando em JAVA e usando o JSF para criar suas páginas. 😊
