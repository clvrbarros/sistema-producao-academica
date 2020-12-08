# sistema-producao-academica
Projeto para a disciplina de Projeto de Software.

# Colaborador
##### GET /api/v1/colaborador -  Lista de todos os colaboradores registrados.
##### GET /api/v1/colaborador/{id} - Consulta por ID do colaborador (requisito funcional 3.a)
##### POST /api/v1/colaborador - Cadastro de Colaborador. Exemplo de corpo de requisição:
```json
{
    "nome": "Cleverson",
    "email": "teste@gmail.com",
    "tipo": "GRADUACAO"
}
onde tipo deve ser: GRADUACAO, MESTRADO, DOUTORADO, PROFESSOR, PESQUISADOR
```
# Projeto de Pesquisa
##### GET /api/v1/projeto - Lista de todos os projetos registrados.
##### GET /api/v1/projeto/{id} - Consulta por ID do projeto (requisito funcional 3.b)
##### POST /api/v1/projeto - Cadastro de Projeto com dados básico. Exemplo de corpo de requisição:
```json
{
    "titulo": "Pesquisa em DataScience",
    "dataInicio": "12/12/2020",
    "dataTermino": "12/12/2022",
    "agenciaFinanciadora": "CNPQ",
    "valorFinanciado": 15000,
    "objetivo": "Aplicação prática",
    "descricao": "Desenvolvimento da pesquisa com o intuito de..."
}
```
##### POST /api/v1/projeto/{id} - Alocação de colaborador no projeto (requisito funcional 1.a). Todas as regras lógicas (ser necessário ter um professor alocado, limite de quantidade para aluno) foram implementadas. O id da URI é o id do projeto. Exemplo de corpo de requisição:
```json
{
    "id": 1
}
onde id é o id do colaborador que será vinculado
```
##### POST /api/v1/projeto/iniciar/{id} - Inicia o projeto (de ELABORACAO para EM ANDAMENTO) - (requisito funcional 1.b.i) Todas as regras lógicas foram implementadas. Não há corpo de requisição. O id da URI é o id do projeto.

##### POST /api/v1/projeto/concluir/{id} - Conclui o projeto (de ANDAMENTO para CONCLUIDO) - (requisito funcional 1.b.ii) Todas as regras lógicas foram implementadas. Não há corpo de requisição. O id da URI é o id do projeto.

# Produção Acadêmica
##### GET /api/v1/publicacao - Lista de todos as publicações.
##### POST /api/v1/publicacao - Cadastro de publicação (requisito funcional 2). Todas as regras lógicas foram implementadas. Exemplo de corpo de requisição:
```json
{
    "titulo":"Artigo sobre ...",
    "conferencia": "SBPC",
    "anoPublicacao": "2019"
}
```
##### POST /api/v1/publicacao/{id}/autores - Vinculação de autor a publicação. O id da URI é o id do projeto. Exemplo de corpo de requisição:
```json
{
    "id": 1
}
onde id é o id do colaborador que será vinculado como um autor da publicação.
```

##### POST /api/v1/publicacao/{id}/projeto - Vinculação de projeto a publicação. O id da URI é o id do projeto. Exemplo de corpo de requisição:
```json
{
    "id": 1
}
onde id é o id do projeto que será vinculado a publicação.
```
# Relatório
##### GET /api/v1/relatorio - Relatorio com as informações do sistema (requisito funcional 4)
