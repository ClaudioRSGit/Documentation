<p align="center"><img src="https://prismatic.io/docs/img/components/icons/ms-sql-server.png" width="200"></p>

<div align="center">

# T-SQL Stored Procedures 
</div>
<br>

# Introdução

Stored Procedures são objetos de base de dados que contêm código T-SQL predefinido. São usados para executar operações específicas na BD de dados de forma eficiente e reutilizável.

## Vantagens das Stored Procedures

- **Diminuição do tráfego na rede:** A execução de scripts no servidor reduz o tráfego de rede causado por aplicações que solicitam ao servidor a execução de instruções SQL.

- **Programação por módulos:**  Stored procedures podem ser chamadas várias vezes pelo código de um programa e alteradas em um único local, independentemente de onde sejam utilizadas.

- **Execução mais rápida:** Stored procedures são compiladas e otimizadas no momento da criação, o que pode resultar numa execução mais rápida em operações com muitas instruções T-SQL ou que são executadas repetidamente.

- **Segurança:** Permite dar permissão aos usuários para executar uma stored procedure, mesmo que não tenham permissão para acessar diretamente o código por meio de um editor.


# Convenções de Nomenclatura

Evitar usar o prefixo "sp_", sendo que é usado para identificar procedimentos da base de dados Master.
Usar nomes simples e descritivos como "uspInsertPerson" para inserir um novo registoo de pessoa.

---
# Sintaxe Básica

````sql
CREATE PROCEDURE <procedure_Name>
AS
BEGIN
    <SQL Statement>
END
````

---

# Exemplos:

## Exemplo 1: Obter todos os clientes

```sql
CREATE PROCEDURE uspGetClient
AS
SELECT *
FROM Customers
```

>Esta stored procedure, chamada uspGetClient, retorna todos os clientes da tabela "Customers".

Chamar StoreProcedure: `EXEC uspGetClient`

## Exemplo 2: Obter clientes de uma cidade específica

```sql
CREATE PROCEDURE uspGetClientCity @City varchar(30)
AS
SELECT *
FROM Customers
WHERE City = @City
```
>Retorna os clientes da tabela "Customers" que estão na cidade fornecida.


Chamar StoreProcedure: `EXEC uspGetClientCity @City = 'Berlin'`

## Exemplo 3: Obter clientes por cidade e endereço

```sql
CREATE PROCEDURE uspGetClientCityAddress
    @City varchar(30) = NULL,
    @Address varchar(60) = NULL
AS
SELECT *
FROM Customers
WHERE City = ISNULL(@City, City)
    AND Address LIKE '%' + ISNULL(@Address, Address) + '%'
```

>Retorna os clientes da tabela "Customers" com base na cidade e no endereço fornecidos.

Chamar StoreProcedure: `EXEC uspGetClientCityAddress @City = 'Berlin'`
<br>
ou
<br>
Chamar StoreProcedure: `EXEC uspGetClientCityAddress @City = 'Madrid', @Address ='Via'`

## Exemplo 4: Quantos Clientes há por cidade

```sql
CREATE PROCEDURE uspGetClientCitiesCount
    @City varchar(30),
    @CitiesCount int OUTPUT
AS
SELECT @CitiesCount = COUNT(*)
FROM Customers
WHERE City LIKE @City
```

>Retorna a quantidade de clientes por cidade.
Chamar StoreProcedure: `DECLARE @Tot int
EXEC uspGetClientCitiesCount @City = 'Madrid', @CitiesCount = @Tot OUTPUT
SELECT @Tot`

## Exemplo 5: Tratamento de Erro em uma Stored Procedure

```sql
ALTER PROCEDURE uspGetClientCitiesCount
    @City varchar(30),
    @CitiesCount int OUTPUT
AS
BEGIN
    SELECT @CitiesCount = COUNT(*)
    FROM Customers
    WHERE City LIKE @City

    RETURN @@ERROR
END
```

>Retorna a quantidade de clientes por cidade e também trata erros

Chamar StoreProcedure: 
```sql
DECLARE @Tot int, @Erro int
EXEC @Erro = uspGetClientCitiesCount @City = 'Madrid', @CitiesCount = @Tot OUTPUT
IF @Erro <> 0
    PRINT 'Ocorreu um erro!'
ELSE
    PRINT 'Numero de registos = ' + CAST(@Tot AS Varchar(10))
    ```