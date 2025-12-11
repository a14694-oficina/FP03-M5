# Ficha Prática 3: Estrutura da Base de Dados

Este repositório contém o *dump* SQL da base de dados **`if0_40156182_modulo5_db`**, que está associada a um projeto de desenvolvimento. O ficheiro `if0_40156182_modulo5_db.sql` inclui a estrutura completa das tabelas (`CREATE TABLE`) e dados de exemplo (`INSERT INTO`) para facilitar a configuração local do ambiente.

## Conteúdo do Ficheiro SQL

O ficheiro foi gerado a partir de um ambiente de alojamento web, especificamente:

| Parâmetro | Detalhe |
| :--- | :--- |
| **Nome da Base de Dados** | `if0_40156182_modulo5_db` |
| **Host** | `sql300.infinityfree.com` |
| **Versão do Servidor** | `11.4.7-MariaDB` |
| **Ferramenta de Exportação** | `phpMyAdmin 4.9.0.1` |
| **Data da Compilação** | 05 de Dezembro de 2025 |

## Estrutura das Tabelas

A base de dados é composta por três tabelas principais: `alunos`, `produtos` e `utilizadores`.

### 1. Tabela `alunos`

Armazena informações sobre os alunos.

| Coluna | Tipo de Dados | Descrição |
| :--- | :--- | :--- |
| **`id`** | `INT(11)` | Chave primária, auto-incremento. |
| **`nome`** | `VARCHAR(100)` | Nome completo do aluno. |
| **`email`** | `VARCHAR(100)` | Endereço de e-mail do aluno. |

**Dados de Exemplo:**

```sql
INSERT INTO `alunos` (`id`, `nome`, `email`) VALUES
(1, 'Ana Silva', 'ana@oficina.pt'),
(2, 'João Costa', 'joao@oficina.pt'),
(3, 'Guilherme Osório', 'a14694@oficina.pt'),
(4, 'José', 'jose@oficina.pt');
```

### 2. Tabela `produtos`

Contém o catálogo de produtos com os respetivos preços.

| Coluna | Tipo de Dados | Descrição |
| :--- | :--- | :--- |
| **`id`** | `INT(11)` | Chave primária, auto-incremento. |
| **`produto`** | `VARCHAR(100)` | Nome do produto. |
| **`preco`** | `DECIMAL(6,2)` | Preço do produto. |

**Dados de Exemplo:**

```sql
INSERT INTO `produtos` (`id`, `produto`, `preco`) VALUES
(1, 'Caderno A5', '3.50'),
(2, 'Caneta Azul', '1.20'),
(3, 'Mochila', '24.90'),
(4, 'Lápis', '2.25');
```

### 3. Tabela `utilizadores`

Utilizada para autenticação de utilizadores.

| Coluna | Tipo de Dados | Descrição |
| :--- | :--- | :--- |
| **`id`** | `INT(11)` | Chave primária, auto-incremento. |
| **`username`** | `VARCHAR(100)` | Nome de utilizador. |
| **`password`** | `VARCHAR(100)` | Palavra-passe do utilizador. |

**Dados de Exemplo:**

```sql
INSERT INTO `utilizadores` (`id`, `username`, `password`) VALUES
(1, 'Osorio', '1234'),
(2, 'pedropaiva', '1234');
```

⚠️ **Aviso de Segurança:** As palavras-passe nesta tabela estão armazenadas em **texto simples** (`1234`). Para um ambiente de produção, é **altamente recomendável** utilizar funções de *hashing* seguras (como `bcrypt`) para proteger as credenciais dos utilizadores.

## Como Utilizar

Para configurar esta base de dados no seu ambiente local, siga os seguintes passos:

1.  Crie uma nova base de dados vazia no seu servidor MySQL/MariaDB (por exemplo, usando o phpMyAdmin, Adminer ou a linha de comandos).
2.  Importe o ficheiro `if0_40156182_modulo5_db.sql` para a base de dados recém-criada.

O ficheiro SQL é um *dump* completo, pelo que irá criar as tabelas e inserir os dados de exemplo automaticamente.
