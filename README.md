# Banco Digital — MySQL

## Sobre o projeto

Este projeto consiste no desenvolvimento de um banco de dados relacional para simular a estrutura inicial de um sistema bancário digital, utilizando MySQL.

O objetivo principal é colocar em prática os conceitos fundamentais de SQL e modelagem de bancos de dados, trabalhando com criação de tabelas, relacionamento entre entidades, inserção, consulta e atualização de informações.

O projeto foi desenvolvido como parte dos meus estudos em Banco de Dados, com foco no aprimoramento dos conhecimentos em MySQL e no desenvolvimento Back-end.

## Tecnologias utilizadas

- MySQL 8.0
- SQL
- MySQL Workbench

## Estrutura do banco de dados

O banco de dados `banco_digital` possui inicialmente duas tabelas principais:

### 1. Tabela clientes

Responsável por armazenar as informações dos clientes cadastrados.

| Campo | Tipo | Descrição |
|---|---|---|
| id | INT | Identificador único do cliente |
| nome | VARCHAR(100) | Nome do cliente |
| cpf | VARCHAR(14) | CPF do cliente |
| email | VARCHAR(100) | E-mail do cliente |

### 2. Tabela contas

Responsável por armazenar as informações das contas bancárias.

| Campo | Tipo | Descrição |
|---|---|---|
| id | INT | Identificador único da conta |
| id_cliente | INT | Referência ao cliente |
| numero_conta | VARCHAR(20) | Número da conta bancária |
| saldo | DECIMAL(15,2) | Saldo disponível na conta |

## Relacionamento entre tabelas

O banco utiliza um relacionamento de um para muitos (1:N).

Um cliente pode possuir várias contas bancárias, enquanto cada conta está vinculada a apenas um cliente.

O relacionamento é estabelecido por meio de uma chave estrangeira (`FOREIGN KEY`), utilizando o campo `id_cliente` da tabela `contas` como referência ao campo `id` da tabela `clientes`.

## Funcionalidades e conceitos praticados

Durante o desenvolvimento, foram trabalhados os seguintes conceitos:

- Criação de banco de dados (`CREATE DATABASE`).
- Criação de tabelas (`CREATE TABLE`).
- Definição de chaves primárias (`PRIMARY KEY`).
- Definição de chaves estrangeiras (`FOREIGN KEY`).
- Restrições de unicidade (`UNIQUE`).
- Inserção de registros (`INSERT INTO`).
- Consulta de informações (`SELECT`).
- Relacionamento entre tabelas (`INNER JOIN`).
- Filtragem de dados (`WHERE`).
- Ordenação de resultados (`ORDER BY`).
- Funções de agregação (`SUM`, `AVG` e `MAX`).
- Atualização de registros (`UPDATE`).

## Exemplos de consultas SQL

### Consultar clientes e suas respectivas contas

```sql
SELECT
    clientes.nome,
    contas.numero_conta,
    contas.saldo
FROM clientes
INNER JOIN contas
ON clientes.id = contas.id_cliente;
```

### Calcular o saldo médio das contas

```sql
SELECT AVG(saldo) AS saldo_medio
FROM contas;
```

### Identificar a conta com maior saldo

```sql
SELECT *
FROM contas
ORDER BY saldo DESC
LIMIT 1;
```

## Objetivo de aprendizagem

Este projeto tem como finalidade consolidar os conhecimentos em bancos de dados relacionais, desenvolver o raciocínio lógico por meio de consultas SQL e compreender como estruturar e manipular informações utilizando MySQL.

Também representa uma etapa da minha preparação para trabalhar com desenvolvimento Back-end, especialmente na integração de bancos de dados com aplicações desenvolvidas em Java e Spring Boot.

## Próximas melhorias

- [ ] Criar uma tabela de transações bancárias.
- [ ] Implementar operações de depósito.
- [ ] Implementar operações de saque.
- [ ] Desenvolver operações de transferência entre contas.
- [ ] Trabalhar com transações SQL (`COMMIT` e `ROLLBACK`).
- [ ] Implementar consultas mais avançadas utilizando `GROUP BY` e `HAVING`.
- [ ] Futuramente, integrar o banco de dados com uma aplicação Java.

---

**Projeto desenvolvido para fins educacionais e prática de SQL e MySQL.**

Desenvolvido por Remilson Santos.
