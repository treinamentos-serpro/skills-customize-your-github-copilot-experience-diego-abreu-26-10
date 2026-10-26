# 📘 Assignment: Building REST APIs with FastAPI

## 🎯 Objective

Construa uma API REST com FastAPI para gerenciar tarefas. Você praticará a criação de endpoints, operações CRUD, validação de dados e testes de uma API HTTP.

## 📝 Tasks

### 🛠️ Criar a aplicação e as primeiras rotas

#### Description
Crie uma aplicação FastAPI para o recurso `tasks` e implemente rotas para verificar se a API está disponível e listar as tarefas. Os dados podem permanecer em memória durante a execução.

#### Requirements
A aplicação concluída deve:

- Criar uma instância de `FastAPI` e iniciar localmente com Uvicorn
- Implementar `GET /health`, retornando um JSON que indique que a API está funcionando
- Implementar `GET /tasks`, retornando uma lista de tarefas em JSON (uma lista vazia inicialmente)
- Exibir a documentação interativa da API em `/docs`


### 🛠️ Implementar operações CRUD para tarefas

#### Description
Adicione operações para criar, consultar, atualizar e remover tarefas. Cada tarefa deve ter um identificador único, um título e um campo que indique se foi concluída.

#### Requirements
A aplicação concluída deve:

- Implementar `POST /tasks` para criar uma tarefa e responder com status HTTP `201`
- Implementar `GET /tasks/{task_id}` para consultar uma tarefa pelo identificador
- Implementar `PUT /tasks/{task_id}` para atualizar o título e o estado de conclusão
- Implementar `DELETE /tasks/{task_id}` para remover uma tarefa
- Retornar status HTTP `404` quando o identificador solicitado não existir


### 🛠️ Validar entradas e testar a API

#### Description
Defina modelos Pydantic para os dados recebidos e retornados pela API. Escreva testes automatizados que exercitem os fluxos principais e os casos de erro.

#### Requirements
A aplicação concluída deve:

- Validar com Pydantic que o título da tarefa não seja vazio e que `completed` seja um valor booleano
- Retornar respostas JSON consistentes para operações bem-sucedidas e erros
- Criar testes usando `TestClient` para criar, listar, consultar, atualizar e remover tarefas
- Verificar nos testes os status HTTP `201`, `404` e o comportamento de validação para entradas inválidas
