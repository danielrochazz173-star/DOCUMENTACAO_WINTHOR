---
title: Conexão Oracle e Ambiente
---

Esta página define o padrão de conexão Oracle usado nos projetos da pasta `E:\FATURAMENTO`, sem expor senhas.

## Requisitos do Oracle Instant Client

Windows:
- Instalar Oracle Instant Client (Basic ou Basic Light)
- Caminho padrão: `C:\oracle\instantclient_23_9`
- Se usar outro caminho, definir `ORACLE_CLIENT_LIB`

Linux:
- Instalar Instant Client (x86_64)
- Dependência: `libaio`
- Definir `ORACLE_CLIENT_LIB=/caminho/instantclient`

## Inicialização do client (modo THICK)

Arquivo de referência: `E:\FATURAMENTO\oracle_init.py`

Fluxo padrão:
1. Verifica se o Instant Client existe
2. Chama `oracledb.init_oracle_client(lib_dir=...)`

## Padrão de credenciais (sem senha em texto)

Use variáveis de ambiente para senha:

```python
DB_HOST = "HOST_ORACLE"
DB_PORT = 1521
DB_SERVICE = "SERVICE_NAME"
DB_USER = "USUARIO"
DB_PASSWORD = os.environ.get("DB_PASSWORD")
```

## Exemplo de conexão segura

```python
import os
import oracledb
from oracle_init import init_oracle

init_oracle()

dsn = oracledb.makedsn("HOST_ORACLE", 1521, service_name="SERVICE_NAME")
conn = oracledb.connect(
    user="USUARIO",
    password=os.environ.get("DB_PASSWORD"),
    dsn=dsn,
)
```

## Boas práticas

- Não salvar senha em arquivos `.md` ou em código versionado
- Centralizar variáveis sensíveis em ambiente ou arquivos `.env` fora do repositório
- Documentar apenas host, porta e service quando necessário
