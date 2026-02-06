---
title: "PowerShell e CMD"
date: 2026-02-06
draft: false
description: "Comandos PowerShell e CMD úteis."
tags: [powershell, cmd, windows]
---

## Listar processos

```powershell
Get-Process | Where-Object { $_.CPU -gt 10 } | Sort-Object CPU -Descending
```

## Copiar arquivos por data

```powershell
Get-ChildItem -Path "C:\Pasta" -Recurse -File |
    Where-Object { $_.LastWriteTime -gt (Get-Date).AddDays(-7) } |
    Copy-Item -Destination "C:\Destino" -Force
```

## CMD: diretório atual

```cmd
cd /d D:\OutroDisco\Pasta
```

## Ver variáveis de ambiente

```powershell
$env:PATH -split ";"
```
