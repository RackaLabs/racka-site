# racka.com.br

Site institucional da **RACKA** — tecnologia, design e estratégia para construir o futuro.

Site estático, sem build e sem dependências: HTML + CSS + JavaScript vanilla.

```
index.html            página única
css/style.css         sistema visual (tokens em DESIGN.md)
js/main.js            menu mobile, reveals, nav ativa
assets/               logo, ícone do carneiro, favicons, og-image
PRODUCT.md, DESIGN.md contexto de marca e design (skill impeccable)
```

## Desenvolvimento local

```bash
python3 -m http.server 8000
# http://localhost:8000
```

## Publicação (GitHub Pages + racka.com.br)

O workflow `.github/workflows/deploy.yml` publica o site no GitHub Pages a cada push na `main`.

Passos únicos de configuração:

1. **Ativar o Pages** — no repositório: *Settings → Pages → Build and deployment → Source: GitHub Actions*.
2. **Domínio customizado** — em *Settings → Pages → Custom domain*, informar `racka.com.br` e marcar *Enforce HTTPS* (o arquivo `CNAME` já está no repositório).
3. **DNS no Registro.br** — na zona de `racka.com.br`:

   | Tipo  | Nome | Valor |
   |-------|------|-------|
   | A     | @    | 185.199.108.153 |
   | A     | @    | 185.199.109.153 |
   | A     | @    | 185.199.110.153 |
   | A     | @    | 185.199.111.153 |
   | CNAME | www  | rackalabs.github.io |

   O subdomínio `viela.racka.com.br` (app Viela) é apontado separadamente para a hospedagem do produto.

## Pendências de conteúdo

- URLs dos perfis (Instagram, LinkedIn, Behance) no rodapé — marcadas com `TODO` no `index.html`.
