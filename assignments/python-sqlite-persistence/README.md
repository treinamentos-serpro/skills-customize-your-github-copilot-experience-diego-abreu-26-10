# 📘 Atividade: Persistência de Dados com SQLite

## 🎯 Objetivo

Use o módulo `sqlite3` do Python para salvar tarefas em um banco de dados local e mantê-las disponíveis após o encerramento do programa. Você praticará criação de tabelas, operações CRUD e integração do banco com uma API existente.

## 📝 Tarefas

### 🛠️ Criar o banco de dados e a tabela de tarefas

#### Descrição
Crie um programa Python que se conecte a um arquivo de banco de dados chamado `tasks.db` e prepare uma tabela para armazenar tarefas. A tabela deve ser criada automaticamente quando o programa for executado pela primeira vez.

#### Requisitos
O programa concluído deve:

- Usar o módulo padrão `sqlite3`, sem exigir um servidor de banco de dados
- Criar a tabela `tasks` com um identificador inteiro como chave primária, um título obrigatório e um campo `completed` com valor padrão falso
- Criar uma função que insira uma tarefa e outra que liste as tarefas em ordem de identificador
- Usar parâmetros SQL (`?`) para passar valores às consultas
- Fechar a conexão com o banco de dados depois de concluir as operações


### 🛠️ Implementar operações CRUD persistentes

#### Descrição
Amplie o programa para permitir consultar, atualizar e excluir tarefas pelo identificador. Verifique o comportamento de cada operação quando a tarefa solicitada não existir.

#### Requisitos
O programa concluído deve:

- Consultar uma tarefa pelo identificador e retornar um resultado claro quando ela não existir
- Atualizar o título e o estado `completed` de uma tarefa existente
- Excluir uma tarefa existente pelo identificador
- Confirmar as alterações com `commit()` e tratar o resultado das operações sem depender de dados mantidos apenas na memória
- Demonstrar que as tarefas continuam disponíveis após fechar e executar o programa novamente


### 🛠️ Conectar a API de tarefas ao SQLite

#### Descrição
Atualize a API de tarefas criada na atividade de FastAPI para usar o banco `tasks.db` em vez de guardar tarefas em uma lista em memória. Mantenha as rotas existentes e verifique que as operações continuam funcionando com o banco de dados.

#### Requisitos
A aplicação concluída deve:

- Inicializar a tabela `tasks` quando a aplicação iniciar
- Usar o SQLite nas rotas para criar, listar, consultar, atualizar e excluir tarefas
- Manter os status HTTP e a validação definidos na API, incluindo `201` ao criar e `404` quando uma tarefa não existir
- Escrever testes que confirmem as operações CRUD e a persistência dos dados entre conexões
- Evitar montar consultas SQL concatenando valores recebidos pela API; usar parâmetros SQL em todas as operações
