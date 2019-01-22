# SpringSecurityAuthenticationPostgreSQL

Esse projeto simples, mostra como criar autenticação utilizando Spring Security + Spring Boot + PostgreSQL.


### Pré-requisitos

Para executar a instalação, desenvolvimento e testes deverá ter instalado as seguintes tecnologias abaixo:

* [Java](https://www.oracle.com/technetwork/java/javase/downloads/jre8-downloads-2133155.html) - Plataforma Java
* [Maven](https://maven.apache.org/) - Ferramenta de automação
* [Spring Boot](http://spring.io/projects/spring-boot/) - Ferramenta facilita a criação de projetos
* [Spring Tool Suite](https://spring.io/tools) - IDE de desenvolvimento
* [PostgreSQL](https://www.postgresql.org/docs/) - Banco de dados relacional
* [Bootstrap](https://getbootstrap.com/docs/4.2/getting-started/introduction/) - Framework front-end


### Testes

Antes de executar a aplicação deverá ser criadas as tabelas e inseridas informações de testes na base de dados.

```
CREATE TABLE users(
   username varchar(20) NOT NULL,
   password varchar(20) NOT NULL,
   enabled boolean NOT NULL DEFAULT FALSE,
   primary key(username)
);

create table user_roles (
  user_role_id SERIAL PRIMARY KEY,
  username varchar(20) NOT NULL,
  role varchar(20) NOT NULL,
  UNIQUE (username,role),
  FOREIGN KEY (username) REFERENCES users (username)
);

INSERT INTO users(username,password,enabled) VALUES ('maria','maria', true);
INSERT INTO users(username,password,enabled) VALUES ('joao','joao', true);
 
INSERT INTO user_roles (username, role) VALUES ('maria', 'ROLE_USER');
INSERT INTO user_roles (username, role) VALUES ('maria', 'ROLE_ADMIN');
INSERT INTO user_roles (username, role) VALUES ('joao', 'ROLE_USER');
```


## Author

* **Lucas A de Miranda Correia** - *Initial work* - [LAMC](https://github.com/lucasagnaldo)
