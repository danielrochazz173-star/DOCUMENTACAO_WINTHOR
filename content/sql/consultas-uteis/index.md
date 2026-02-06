---
title: "Consultas úteis"
date: 2026-02-06
draft: false
description: "Consultas SQL prontas para uso no dia a dia."
tags: [sql, consultas, select]
---

## Listar tabelas (SQL Server)

```sql
SELECT TABLE_SCHEMA, TABLE_NAME
FROM INFORMATION_SCHEMA.TABLES
WHERE TABLE_TYPE = 'BASE TABLE'
ORDER BY TABLE_SCHEMA, TABLE_NAME;
```

## Listar colunas de uma tabela

```sql
SELECT COLUMN_NAME, DATA_TYPE, IS_NULLABLE, CHARACTER_MAXIMUM_LENGTH
FROM INFORMATION_SCHEMA.COLUMNS
WHERE TABLE_NAME = 'NOME_DA_TABELA'
ORDER BY ORDINAL_POSITION;
```

## Top N por grupo

```sql
SELECT *
FROM (
    SELECT *,
           ROW_NUMBER() OVER (PARTITION BY grupo ORDER BY data DESC) AS rn
    FROM MinhaTabela
) t
WHERE rn <= 10;
```

## Datas: início e fim do mês

```sql
SELECT
    DATEFROMPARTS(YEAR(GETDATE()), MONTH(GETDATE()), 1) AS inicio_mes,
    EOMONTH(GETDATE()) AS fim_mes;
```

## Contar por agrupamento

```sql
SELECT coluna, COUNT(*) AS total
FROM Tabela
WHERE condicao = 1
GROUP BY coluna
ORDER BY total DESC;
```
