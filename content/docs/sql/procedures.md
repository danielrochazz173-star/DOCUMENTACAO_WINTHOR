---
title: Procedures e funções
---

## Template de procedure

```sql
CREATE OR ALTER PROCEDURE dbo.NomeDaProcedure
    @Param1 INT,
    @Param2 VARCHAR(100) = NULL
AS
BEGIN
    SET NOCOUNT ON;

    SELECT ...
    FROM ...
    WHERE ...
END;
GO
```

## Template de função escalar

```sql
CREATE OR ALTER FUNCTION dbo.NomeDaFuncao (@Valor INT)
RETURNS VARCHAR(50)
AS
BEGIN
    DECLARE @Resultado VARCHAR(50);
    SET @Resultado = CAST(@Valor AS VARCHAR(50));
    RETURN @Resultado;
END;
GO
```

## Listar procedures do banco

```sql
SELECT name, create_date, modify_date
FROM sys.procedures
ORDER BY name;
```
