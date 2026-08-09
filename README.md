# pg-roteiro-iniciantes - Um Gui prático para o primeiro mês de estudos com PostgreSQL

Este repositório é o complemento para a palestra **"Se o Postgres é o caminho, por onde começar?"**, apresentada na **PGConf Brasil 2026**

O objetivo deste guia é fornecer um ambiente rápido em Docker e um roteiro estruturado para apoio do aprendizado do PostgreSQL, que abrange navegar na documentação oficial do PostgreSQL e fazer uso da IA (LLMs) como ferramenta cumprindo o papel de tutora.

---

## Como Subir o Ambiente de Estudos

Certifique-se de ter o **Docker** e o **Docker Compose** instalados em sua máquina.

1. Clone este repositório:

```bash
   git clone [https://github.com/isonux/pg-roteiro-iniciantes.git](https://github.com/isonux/pg-roteiro-iniciantes.git)
   cd pg-roteiro-iniciantes

```

2. Suba o banco de dados PostgreSQL usando o `docker-compose`:

```bash
docker compose up -d

```


3. Conecte-se ao terminal do PostgreSQL (`psql`):
```bash
docker exec -it pg_estudos psql -U estudante -d lab_postgres

```



---

## Roteiro de Estudos de 4 Semanas

### Semana 1: Mão na Massa com Docker

* **Objetivo:** Perder o medo do terminal, subir o ambiente e ler a Parte I da documentação oficial
* **O que estudar na Documentação:**
* [PostgreSQL Tutorial (Parte I)](https://www.postgresql.org/docs/current/tutorial.html)


* **Atividades Práticas:**
1. Conectar via `psql` e aprender comandos meta (`\l`, `\dt`, `\d nome_tabela`, `\q`)
2. Executar comandos básicos de DDL (`CREATE TABLE`) e DML (`INSERT`, `SELECT`)


* **Prompt para usar com a IA:**
> *"Atue como um tutor experiente em PostgreSQL. Estou aprendendo a utilizar o utilitário psql via linha de comando. Me explique a diferença entre comandos SQL normais e comandos meta (iniciados com barra invertida `\`), dando 3 exemplos práticos de uso do psql"*



---

### Semana 2: Modelagem, Tipos de Dados e Constraints

* **Objetivo:** Entender a estrutura lógica dos dados, tipos principais e como garantir a integridade
* **O que estudar na Documentação:**
* [Data Types](https://www.postgresql.org/docs/current/datatype.html) (Focar em `integer`, `text`, `boolean`, `timestamp`, `numeric`)
* [Constraints](https://www.postgresql.org/docs/current/ddl-constraints.html) (`NOT NULL`, `UNIQUE`, `PRIMARY KEY`, `FOREIGN KEY`)


* **Atividades Práticas:**
1. Criar um esquema simples para um blog ou loja virtual (Tabelas: `usuarios`, `pedidos` / `posts`)
2. Testar o comportamento ao tentar inserir dados inválidos em colunas com restrições


* **Prompt para usar com a IA:**
> *"Explique o que é uma Foreign Key no PostgreSQL e por que ela é importante? Me dê exemplos praticos que posso utilizar em meu laboratório"*


---

### Semana 3: Relacionamentos (JOINs) e Introdução ao EXPLAIN

* **Objetivo:** Cruzar dados entre tabelas e entender como o Postgres executa uma consulta
* **O que estudar na Documentação:**
* [Queries - Joins](https://www.postgresql.org/docs/current/queries-table-expressions.html#QUERIES-FROM)
* [Using EXPLAIN](https://www.postgresql.org/docs/current/using-explain.html)


* **Atividades Práticas:**
1. Executar consultas usando `INNER JOIN`, `LEFT JOIN` e `GROUP BY` com funções de agregação (`COUNT`, `SUM`)
2. Rodar o comando `EXPLAIN` antes de uma query e identificar o custo inicial e final


* **Prompt para usar com a IA:**
> *"Cole aqui um erro que você recebeu ao tentar rodar um GROUP BY. Exemplo: 'Recebi o erro ERROR: column X must appear in the GROUP BY clause or be used in an aggregate function. Explique por que o Postgres exige isso e como posso corrigir minha query de forma segura'"*



---

### Semana 4: Transações e Conexão com Aplicação

* **Objetivo:** Garantir a consistência das operações (`ACID`) e conectar o banco a uma aplicação simples
* **O que estudar na Documentação:**
* [Transactions](https://www.postgresql.org/docs/current/tutorial-transactions.html)


* **Atividades Práticas:**
1. Testar comandos de controle de transação (`BEGIN`, `COMMIT`, `ROLLBACK`, `SAVEPOINT`).
2. Conectar ao banco a partir de uma linguagem de sua preferência (Python, Node.js, Java, etc.) ou via cliente gráfico (DBeaver/pgAdmin)


* **Prompt para usar com a IA:**
> *"Me dê um exemplo simples de cenário do mundo real em que o uso do ROLLBACK em uma transação impede a corrupção de dados em uma transferência financeira"*
