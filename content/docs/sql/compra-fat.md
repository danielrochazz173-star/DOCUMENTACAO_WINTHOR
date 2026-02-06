---
title: Compras (COMPRA_FAT) - Visão de Dados
---

Esta página resume a base de dados e as métricas usadas no sistema de visualização de compras.

## Objetivo

Consolidar as consultas que sustentam:
- Top produtos por valor
- Distribuição por departamentos
- Positivação (clientes únicos) por vendedor
- Visão mensal ou anual

## Fontes de dados (alto nível)

As consultas combinam:
- Tabelas de entradas/compras (ex: `PCNFENT`, `PCMOV`)
- Tabelas de vendas por cliente para positivação (ex: `PCPEDC`, `PCPEDI`)

## Métricas principais

- Valor comprado por produto
- Top N produtos por período
- Distribuição por departamento
- Positivação: clientes únicos no período

## Filtros comuns

- Período: mês específico ou ano completo
- Departamento: específico ou todos
- Top N: quantidade de itens exibidos

## Observações de negócio

- Positivação considera clientes únicos no período
- Um cliente conta uma vez, mesmo com múltiplas compras
- Quando "Ano completo" estiver ativo, o mês é ignorado

## Execução do sistema

```bash
python visualizacao_compras_produtos.py
```
