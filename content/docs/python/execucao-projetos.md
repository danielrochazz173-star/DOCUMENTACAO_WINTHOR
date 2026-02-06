---
title: Execução dos Projetos
---

Guia rápido para executar os principais projetos com Python.

## Compra_FAT - Visualização de Compras

```bash
python visualizacao_compras_produtos.py
```

Recursos:
- Top produtos por valor
- Gráfico por departamento
- Positivação (clientes únicos)
- Dashboard completo

## Análise de Vendedores (Excel)

```bash
python analise_vendedores_excel.py
```

Instalação:
- `INSTALAR_DEPENDENCIAS_ANALISE_VENDEDORES.bat`
- Dependências: `oracledb`, `pandas`, `openpyxl`

## Negociações e Comissões (Google Sheets)

```bash
python sistema_negociacoes_comissao.py
```

Dependências:
- `gspread`
- `google-auth`

## Dashboard Anual de Vendedores (Streamlit)

```bash
streamlit run dashboard_analise_vendedores.py
```

Abre em: `http://localhost:8501`

## Monitor de Boletos (API)

```bash
cd E:\FATURAMENTO\MONITOR_BOLETOS\backend
python main.py
```

API padrão: `http://localhost:8000`

## Campanhas Camil (Flask)

```bash
cd E:\FATURAMENTO\CAMPANHAS-CAMIL
python app.py
```

Abre em: `http://localhost:5000`
