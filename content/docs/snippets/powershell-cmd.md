---
title: PowerShell e CMD
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
