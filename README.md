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

## Objetivo
Desenvolver um CRUD da entidade 'Project'

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



