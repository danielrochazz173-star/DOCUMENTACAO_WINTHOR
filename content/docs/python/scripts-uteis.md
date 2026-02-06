---
title: Scripts úteis
---

## Ler CSV e mostrar colunas

```python
import pandas as pd

df = pd.read_csv("arquivo.csv", encoding="utf-8", sep=";")
print(df.columns.tolist())
print(df.head())
```

## Conectar SQL Server (pyodbc)

```python
import pyodbc

conn = pyodbc.connect(
    "DRIVER={ODBC Driver 17 for SQL Server};"
    "SERVER=servidor;DATABASE=banco;UID=user;PWD=senha"
)
cursor = conn.cursor()
cursor.execute("SELECT TOP 10 * FROM Tabela")
for row in cursor.fetchall():
    print(row)
conn.close()
```

## Listar arquivos de uma pasta

```python
from pathlib import Path

pasta = Path(r"C:\Pasta")
for f in pasta.glob("*.csv"):
    print(f.name, f.stat().st_mtime)
```

## Rodar com argumentos

```python
import sys

if len(sys.argv) < 2:
    print("Uso: python script.py <arquivo>")
    sys.exit(1)
arquivo = sys.argv[1]
```
