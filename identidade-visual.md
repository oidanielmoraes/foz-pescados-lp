# Identidade Visual — Foz Pescados

---

## 1. Tipografia

### Família: Futura (via Adobe Fonts / Typekit)

```html
<link rel="stylesheet" href="https://use.typekit.net/kdl2ihv.css">
```

Adicionar no `<head>` antes de qualquer CSS do projeto.

**Pesos disponíveis e utilizados:**

| Peso | CSS font-weight | Uso |
|------|----------------|-----|
| Light | 300 | Títulos grandes e hero — elegância |
| Book / Regular | 400 | Corpo de texto |
| Medium | 500 | Destaques inline, lead text |
| Bold | 700 | Títulos de seção, botões, labels |
| Extra Bold / Heavy | 800 | Display, números de impacto |

---

### Escala Tipográfica

**Ratio:** Perfect Fourth — 1.333
**Base:** 16px
**Abordagem:** Fluid type com `clamp()` — escala entre mobile (375px) e desktop (1440px)

```css
:root {
  /* === ESCALA TIPOGRÁFICA === */

  /* Display — Hero headline, números de impacto */
  --text-display: clamp(3.5rem, 7vw, 6rem);        /* 56px → 96px */

  /* H1 — Título principal de seção */
  --text-h1: clamp(2.5rem, 5vw, 4rem);             /* 40px → 64px */

  /* H2 — Título de bloco */
  --text-h2: clamp(1.75rem, 3.5vw, 2.75rem);       /* 28px → 44px */

  /* H3 — Subtítulo de card / item */
  --text-h3: clamp(1.25rem, 2.5vw, 1.75rem);       /* 20px → 28px */

  /* H4 — Eyebrow / label de seção */
  --text-h4: clamp(0.875rem, 1.5vw, 1rem);         /* 14px → 16px */

  /* Lead — Subtítulo hero, parágrafo de destaque */
  --text-lead: clamp(1.125rem, 2vw, 1.375rem);     /* 18px → 22px */

  /* Body — Corpo de texto padrão */
  --text-body: 1rem;                                /* 16px */

  /* Body Small — Informação secundária */
  --text-body-sm: 0.875rem;                         /* 14px */

  /* Caption / Legenda — Crédito, notas */
  --text-caption: 0.75rem;                          /* 12px */

  /* Tag / Eyebrow — Rótulos, categorias, selos */
  --text-tag: 0.6875rem;                            /* 11px */

  /* Button */
  --text-button: 0.8125rem;                         /* 13px */
}
```

---

### Regras de Uso Tipográfico

| Nível | Peso | Case | Letter-spacing | Line-height |
|-------|------|------|---------------|-------------|
| Display | 800 ExtraBold | UPPERCASE ou Title | -0.02em | 1.0 |
| H1 | 700 Bold | Title Case | -0.01em | 1.1 |
| H2 | 700 Bold | Title Case | 0 | 1.2 |
| H3 | 500 Medium | Title Case | 0 | 1.3 |
| H4 Eyebrow | 700 Bold | UPPERCASE | +0.12em | 1.4 |
| Lead | 300 Light | Sentence | 0 | 1.6 |
| Body | 400 Book | Sentence | 0 | 1.7 |
| Body Small | 400 Book | Sentence | 0 | 1.6 |
| Caption | 400 Book | Sentence | +0.04em | 1.5 |
| Tag | 700 Bold | UPPERCASE | +0.14em | 1 |
| Button | 700 Bold | UPPERCASE | +0.10em | 1 |

**Princípios:**
- Futura Light em títulos grandes = elegância máxima. Reservar ExtraBold para poucos momentos de força
- Tags, labels e botões em uppercase + tracking generoso são a assinatura visual da Futura
- Nunca usar Futura Light abaixo de 16px — legibilidade cai muito em pesos leves pequenos
- Contraste dramático entre Display e Body cria hierarquia clara

---

## 2. Sistema de Cores

### Paleta Confirmada

```css
:root {
  /* === PALETA PRIMÁRIA === */
  --color-cream:     #FFFAF0;   /* Bege claro */
  --color-navy:      #1A3B6B;   /* Azul-mar */
  --color-red:       #852824;   /* Vermelho frescor */
  --color-brown:     #5E3C20;   /* Marrom */

  /* === PALETA SECUNDÁRIA === */
  --color-sky:       #AFC1CB;   /* Azul claro */
  --color-wine:      #4C1C12;   /* Marrom vinho */
  --color-terracota: #A45E37;   /* Terracota-queimado */
  --color-yellow:    #EFA625;   /* Amarelo âmbar */
}
```

**Nota:** As cores `#FFFAF0` (cream) e `#1A3B6B` (navy) são as cores nativas dos SVGs de logo, selos e ilustrações. O sistema de cores foi projetado para funcionar diretamente com os assets sem conversão.

---

### Lógica de Uso

| Cor | Uso principal |
|-----|--------------|
| `cream` | Background padrão — seções claras, hero com imagem escura |
| `navy` | Institucional — fundos escuros, botão primário, header |
| `red` | Ação / urgência — CTA principal, hover, badges |
| `brown` | Texto sobre fundo claro |
| `sky` | Suporte — backgrounds de cards, campos de formulário |
| `wine` | Premium escuro — seções de depoimento, fundo alternativo |
| `terracota` | Accent quente — ícones decorativos, bordas de destaque |
| `yellow` | Destaque de valor — selos de credibilidade, números |

### Combinações Validadas

```
Fundo Navy    → Texto Cream       ✓ Alto contraste, institucional
Fundo Cream   → Texto Brown       ✓ Sofisticado, legível
Fundo Wine    → Texto Cream       ✓ Premium escuro
Fundo Sky     → Texto Navy        ✓ Leve, informativo
Fundo Cream   → CTA Navy          ✓ Botão primário
Fundo Navy    → Badge Yellow      ✓ Selo de destaque
Fundo Navy    → Ilustração Cream  ✓ Silhuetas de pescados sobre fundo escuro
Fundo Cream   → Ilustração Navy   ✓ Cards curadoria sobre fundo claro
```

---

### Tokens CSS

```css
:root {
  --surface-default:  var(--color-cream);
  --surface-dark:     var(--color-navy);
  --surface-deeper:   var(--color-wine);
  --surface-subtle:   var(--color-sky);

  --text-primary:     var(--color-brown);
  --text-on-dark:     var(--color-cream);
  --text-heading:     var(--color-navy);
  --text-muted:       #8A7A6A;

  --action-primary:   var(--color-navy);
  --action-danger:    var(--color-red);
  --action-accent:    var(--color-terracota);
  --action-highlight: var(--color-yellow);
}
```

---

## 3. Catálogo de Assets SVG

Todos os arquivos estão em `svgs/`. Usar inline SVG para controle máximo de cor e performance.

---

### Logos

| Arquivo | Cor nativa | Quando usar |
|---------|-----------|-------------|
| `Logo_Azul.svg` | Navy `#1A3B6B` | Fundo claro (cream, white, sky) |
| `Logo_Offwhite.svg` | Cream `#FFFAF0` | Fundo escuro (navy, wine) |
| `Logo_Preto.svg` | Preto | Impressão, documentos, contextos neutros |

**Estrutura do logo:** Logotipo completo com símbolo (dois peixes), wordmark "FOZ", tagline "CURADORIA DE PESCADOS" e referência "DESDE 2011". `viewBox="0 0 992.85 315.1"` — proporção aproximada 3:1.

```css
.logo { width: 200px; height: auto; }        /* header desktop */
.logo--mobile { width: 140px; height: auto; } /* header mobile */
```

---

### Selos de Credibilidade

| Arquivo | Formato | Conteúdo | Contexto |
|---------|---------|---------|---------|
| `selo-curadoria de pescados.svg` | Oval vertical (231×375) | "CURADORIA DE PESCADOS" + símbolo Foz + "DESDE 2011" | Seção de credenciais, rodapé |
| `selo-produtobrasileiro.svg` | Oval vertical (136×197) | "PRODUTO BRASILEIRO" + elipses concêntricas | Seção de origem, curadoria |
| `selo-qualidade-premium.svg` | Banner horizontal (179×108) | "QUALIDADE PREMIUM" | Hero, seção de diferenciais |

**Cores nativas:** Todos os selos usam cream `#FFFAF0` + navy `#1A3B6B`. Funcionam melhor sobre fundos neutros ou com uma sutil sombra quando sobre fundos brancos.

```html
<!-- Exemplo de uso inline com controle de tamanho -->
<div class="seal">
  <!-- colar SVG do selo aqui -->
</div>
```

```css
.seal { width: 80px; height: auto; }
.seal--large { width: 120px; }
```

---

### Ilustrações de Produto — Silhuetas

Silhuetas em cream `#FFFAF0`. Projetadas para uso sobre **fundo escuro** (navy, wine). O `fill` está hardcoded no SVG — para mudar de cor, substituir `#fffaf0` no código.

| Arquivo | Dimensões (px) | Proporção | Espécie |
|---------|---------------|-----------|---------|
| `pirarucu.svg` | 424×113 | Horizontal longa | Pirarucu |
| `salmao.svg` | 369×122 | Horizontal | Salmão |
| `bacalhau.svg` | 379×140 | Horizontal | Bacalhau |
| `tilapia.svg` | 299×164 | Horizontal | Tilápia |
| `atum.svg` | 287×128 | Horizontal | Atum |
| `peixe.svg` | 242×106 | Horizontal | Peixe genérico |
| `camarao.svg` | 214×135 | Horizontal | Camarão |
| `polvo.svg` | 242×241 | Quadrada | Polvo |
| `lagosta.svg` | 249×250 | Quadrada | Lagosta |
| `carangueijo.svg` | 260×197 | Levemente vertical | Caranguejo |

**Uso sugerido:** Dispostas em fila horizontal como decoração de seção sobre fundo navy — transmitem variedade e presença do portfólio.

---

### Ilustrações de Curadoria — Cards

Ilustrações detalhadas em navy `#1A3B6B` (linha fina), projetadas para uso sobre **fundo claro** (cream). Formato predominante ~188×209px. Usam `xlink` — incluir o arquivo SVG completo.

| Arquivo | Dimensões (px) | Espécie |
|---------|---------------|---------|
| `curadoria-pirarucu.svg` | 188×209 | Pirarucu |
| `curadoria-camarao.svg` | 188×209 | Camarão |
| `curadoria-carangueijo.svg` | 188×209 | Caranguejo |
| `curadoria-polvo.svg` | 188×209 | Polvo |
| `curadoria-ovas.svg` | 188×209 | Ovas |
| `curadoria-lagosta.svg` | 282×278 | Lagosta |

**Uso sugerido:** Cards do portfólio — uma ilustração por categoria, acompanhada de nome e descrição da espécie.

---

## 4. Uso Técnico dos SVGs

### Inline SVG (padrão para todos os assets)

```html
<!-- Logo no header -->
<a href="/" aria-label="Foz Pescados">
  <!-- conteúdo de Logo_Azul.svg -->
</a>

<!-- Selo de credibilidade -->
<figure class="seal" aria-label="Curadoria de Pescados desde 2011">
  <!-- conteúdo de selo-curadoria de pescados.svg -->
</figure>

<!-- Silhueta decorativa -->
<div class="fish-silhouette" aria-hidden="true">
  <!-- conteúdo de pirarucu.svg -->
</div>
```

### Controle de cor via CSS

Os paths dos selos e logos usam classes `.cls-1` e `.cls-2`. Para sobrescrever a cor via CSS quando necessário:

```css
/* Inverter logo para uso em fundo colorido (alternativa ao uso de Logo_Offwhite) */
.header--dark .logo .cls-1 { fill: #FFFAF0; }
```

### Tamanhos recomendados

```css
/* Logo */
.logo-header    { width: clamp(120px, 18vw, 200px); }
.logo-footer    { width: clamp(100px, 14vw, 160px); }

/* Selos */
.seal-sm        { width: 70px; }
.seal-md        { width: 100px; }
.seal-lg        { width: 130px; }

/* Silhuetas decorativas (fundo navy) */
.fish-hero      { width: clamp(160px, 25vw, 280px); }
.fish-strip     { width: clamp(80px, 12vw, 160px); }

/* Cards curadoria */
.curadoria-card-img { width: 120px; }
```

---

## 5. Cheat Sheet

```
FONTE
──────────────────────────────────────────────
Adobe Fonts: https://use.typekit.net/kdl2ihv.css
Fallback: "Century Gothic", "Trebuchet MS", sans-serif

TIPOGRAFIA
──────────────────────────────────────────────
Display    → 56–96px  | 800 | UPPER | -0.02em | lh 1.0
H1         → 40–64px  | 700 | Title | -0.01em | lh 1.1
H2         → 28–44px  | 700 | Title |       0 | lh 1.2
H3         → 20–28px  | 500 | Title |       0 | lh 1.3
H4 Eyebrow → 14–16px  | 700 | UPPER | +0.12em | lh 1.4
Lead       → 18–22px  | 300 | —     |       0 | lh 1.6
Body       → 16px     | 400 | —     |       0 | lh 1.7
Body Sm    → 14px     | 400 | —     |       0 | lh 1.6
Caption    → 12px     | 400 | —     | +0.04em | lh 1.5
Tag        → 11px     | 700 | UPPER | +0.14em | lh 1.0
Button     → 13px     | 700 | UPPER | +0.10em | lh 1.0

CORES PRIMÁRIAS
──────────────────────────────────────────────
Cream      #FFFAF0   Background padrão / textos sobre escuro
Navy       #1A3B6B   Institucional / CTA / ilustrações curadoria
Red        #852824   Ação / urgência
Brown      #5E3C20   Texto sobre fundo claro

CORES SECUNDÁRIAS
──────────────────────────────────────────────
Sky        #AFC1CB   Suporte / cards
Wine       #4C1C12   Fundos premium escuros
Terracota  #A45E37   Accents quentes
Yellow     #EFA625   Selos / números de impacto

ASSETS SVG (pasta: svgs/)
──────────────────────────────────────────────
Logos      3 versões: Azul (sobre claro) | Offwhite (sobre escuro) | Preto
Selos      3 peças: Curadoria de Pescados | Produto Brasileiro | Qualidade Premium
Silhuetas  10 espécies em cream — usar sobre navy/wine
Curadoria  6 cards em navy — usar sobre cream
```
