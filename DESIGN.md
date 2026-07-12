# Design

Sistema visual do site RACKA (racka.com.br). Fonte da verdade: mockup fornecido pelo cliente (jul/2026) + lockup da marca.

## Theme

Instrumento de precisão: superfícies quase-pretas abrem e fecham a página; o miolo roda em off-white quente. HUD marks (crosshairs, dot grids, anéis, kickers `//`) são a gramática decorativa da marca — usados com parcimônia e propósito.

## Color

Tokens em OKLCH (`css/style.css`):

| Token | Valor | Uso |
|---|---|---|
| `--ink-950` | `oklch(0.155 0.004 80)` (≈#0A0A0A) | bg hero, CTA, footer |
| `--ink-900` | `oklch(0.21 0.005 80)` | superfícies elevadas no escuro |
| `--ink` | `oklch(0.19 0.008 80)` (≈#14120F) | texto em fundo claro |
| `--paper` | `oklch(0.955 0.008 90)` (≈#F2EFEA) | bg seções claras |
| `--paper-2` | `oklch(0.935 0.01 90)` | bg alternado (Destaque) |
| `--orange` | `oklch(0.665 0.235 34)` (≈#FF4700) | acento display, botões, kickers no escuro |
| `--orange-ink` | `oklch(0.545 0.20 36)` (≈#C93E00) | acento em texto pequeno sobre claro (AA) |
| `--lilac` | `oklch(0.76 0.095 295)` (≈#B9A7E6) | traços de sublinhado |
| `--mist` | `oklch(0.78 0.01 80)` | texto secundário no escuro |

Estratégia: **Committed** — preto + laranja carregam a identidade; lilás é assinatura pontual.

## Typography

- **Display/headings:** Archivo (variável), 800–900, caps, tracking −0.02em, `text-wrap: balance`. Escala fluida com `clamp()`, teto 6rem.
- **Body:** Archivo 400/500, 1rem–1.125rem, medida ≤65ch.
- **HUD/labels:** Fragment Mono 400, caps, 11–13px, tracking 0.08–0.18em. Usada em kickers, nav, botões, stats labels.
- **Exceção Viela:** Pacifico apenas no wordmark do produto Viela dentro do phone mockup (marca do produto, não da RACKA).

## Components

- **Kicker:** `// NOME` em mono caps — laranja-ink sobre claro, laranja sobre escuro. Sistema deliberado da marca (presente no mockup em todas as seções).
- **Botão primário:** retângulo branco, label mono caps ink, quadrado laranja acoplado com seta →; hover desloca a seta e escurece o quadrado.
- **Link-seta:** mono caps + seta, sublinhado por hairline; hover em laranja.
- **Stroke lilás:** traço curto (56–72px × 5px) sob headings, sempre à esquerda.
- **HUD marks:** crosshair de cantos, dot grid 4×4, plus grid, anéis (1 sólido fino + 1 pontilhado) girando lento.
- **Hairlines:** 1px `currentColor` a 12–18% de opacidade para réguas e divisores.

## Layout

Container 1200px, padding lateral `clamp(20px, 5vw, 56px)`. Seções com respiro `clamp(96px, 12vw, 160px)`. Composições assimétricas texto-esquerda / objeto-direita; stats com réguas horizontais; pilares de tecnologia divididos por hairlines verticais.

## Motion

Ease-out expo (`cubic-bezier(0.16, 1, 0.3, 1)`), 500–700ms. Entrada do hero coreografada no load; reveals por IntersectionObserver que só aprimoram conteúdo já visível; anéis HUD em rotação contínua lenta. Tudo desligado sob `prefers-reduced-motion: reduce`.

## Assets

- `assets/logo-white.png` — wordmark RACKA branco (extraído do lockup original).
- `assets/ram-white.png` — ícone do carneiro branco.
- `assets/favicon.png`, `assets/apple-touch-icon.png`, `assets/icon-512.png`, `assets/og-image.png`.
- Ilustrações do device (hero) e da cena Viela: SVG inline autoral em `index.html`.
