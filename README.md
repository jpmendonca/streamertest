# STREAMER-TEST API

Essa aplicação foi criada com o intuito de testar os conhecimentos básicos de um desenvolvedor **.net core**.

Trata-se de uma API Rest, com acesso a um banco de dados SQL contendo apenas uma entidade 'Courses'.

## ESTRUTURA BÁSICA
               
**./Data**  
Contexto do banco de dados                  

**./Model**  
Modelagem do banco de dados

**./Services**  
Classes de serviços de acesso ao banco de dados

**./SS_DB.db**  
Sqlite DB

## O que fazer?
Desenvolver um CRUD da entidade 'Project'.

Fique a vontade para programar como você costuma programar. Será analisada a organização, criatividade e boas-práticas do código. Como trata-se apenas de um teste, qualquer dúvida que surgir no meio do caminho, resolva como você achar que é mais coerente.

### Model
Criar a seguinte tabela, através do Code-First do Entity Framework Core.

**Table:** Projects

| **Nome**        | **Tipo**              |
|-----------------|-----------------------|
| Id              | Int                   |
| Name            | String [REQUIRED]     |
| Image           | String                |
| Why             | String                |
| What            | String                |
| WhatWillWeDo    | String                |
| ProjectStatus   | ProjectStatus (Enum)  |
| Course          | Course [REQUIRED]     |  
| CourseId        | Int (FK de Course)    |

#### Relacionamentos  
1 Course / N Project | OnDelete.Cascade

#### ProjectStatus (Enum)
0 - Em desenvolvimento  
1 - Publicado

### Services
Criar uma classe com os serviços necessários para realizar a criação, edição, remoção e listagem da entidade Project via DBContext (./Data/StreamerContext.cs)

### Controller
Realizar a injeção de dependência da classe de serviços e criar os seguintes métodos:

#### GetById
[HttpGet]  
Recebe um ID de um 'Project'.  
Retorna um objeto do tipo 'Project'.

#### GetByCourse
[HttpGet]  
Recebe um ID de um 'Course'.  
Retorna uma lista genérica de 'Project'.

#### Update
[HttpPut]  
Recebe um objeto do tipo 'Project' e realiza a atualização do mesmo.  
Retorna um valor booleano.

#### Delete
[HttpDelete]  
Recebe um ID de um 'Course' e realiz a remoção do mesmo.  
Retorna um valor booleano.

#### Create
[HttpPost]  
Recebe um objeto do tipo Project e realiza a inserção no banco de dados.
Retorna o Id do 'Project' inserido.

