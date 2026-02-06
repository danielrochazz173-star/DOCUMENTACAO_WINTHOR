---
title: Exemplos e trechos
---

## Dict com default

```python
from collections import defaultdict

d = defaultdict(list)
d["chave"].append("valor")
```

## Data e hora formatada

```python
from datetime import datetime

agora = datetime.now()
print(agora.strftime("%Y-%m-%d %H:%M:%S"))
```

## Tratar encoding em arquivo

```python
with open("arquivo.txt", "r", encoding="utf-8", errors="replace") as f:
    conteudo = f.read()
```

## Log simples

```python
import logging

logging.basicConfig(level=logging.INFO)
logger = logging.getLogger(__name__)
logger.info("Mensagem")
```

## Requisição HTTP

```python
import requests

r = requests.get("https://exemplo.com/api")
r.raise_for_status()
dados = r.json()
```
