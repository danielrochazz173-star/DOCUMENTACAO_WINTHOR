# DICON – Documentação

Site de documentação interna (Hugo + Hextra): SQL, Python e snippets.

## Rodar local

- Instale [Hugo Extended](https://gohugo.io/installation/).
- Na raiz do repositório:

```bash
hugo server
```

Abre em `http://localhost:1313`.

## Publicar no GitHub Pages

1. Faça push deste repositório com o workflow em `.github/workflows/pages.yaml` para o GitHub.
2. No repositório: **Settings → Pages → Source** = **GitHub Actions**.
3. O workflow sobe o site a cada push na branch `main`.

Se este repo for só a documentação (conteúdo na raiz), rode o workflow sem `working-directory` e com `path: ./public`, e no `hugo.yaml` use:

`baseURL: "https://SEU_USER.github.io/NOME_DO_REPO/"`

## Onde colocar o quê

- **SQL:** `content/sql/` (consultas, procedures).
- **Python:** `content/python/` (scripts, exemplos).
- **Snippets:** `content/snippets/` (PowerShell, CMD, outros).

Cada página é um `.md` dentro da pasta da seção; use `index.md` para a página da seção.
