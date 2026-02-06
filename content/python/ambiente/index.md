---
title: Ambiente e Dependências
---

Esta página define o padrão de ambiente para rodar os projetos em `E:\FATURAMENTO`.

## Python

- Versão recomendada: 3.8 ou superior
- Preferir ambiente virtual por projeto

## Dependências base

Arquivo principal: `E:\FATURAMENTO\requirements.txt`

Principais grupos:
- Conexão e dados: `oracledb`, `pandas`, `openpyxl`
- Gráficos: `plotly`, `kaleido`
- Dashboards: `streamlit`
- APIs: `Flask`, `FastAPI`, `uvicorn`, `pydantic`
- PDF: `reportlab`, `Pillow`

## Exemplo de setup

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
```

## Oracle Instant Client

Requisito para conexão Oracle (modo THICK):
- Windows: `C:\oracle\instantclient_23_9`
- Se o caminho for diferente, usar `ORACLE_CLIENT_LIB`

## Boas práticas

- Evitar senha em texto puro
- Usar variáveis de ambiente para credenciais
