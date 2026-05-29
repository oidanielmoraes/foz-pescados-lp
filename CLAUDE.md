# Foz Pescados — Landing Page

Landing page estática (HTML/CSS/JS puro) para geração de leads B2B. Sem build, sem framework, sem dependências além da Adobe Fonts.

**Arquivo principal:** `index.html` (~1300 linhas, tudo em um único arquivo)

---

## O que é o projeto

Landing page da **Foz Pescados** — curadoria de pescados para foodservice premium. O site não é e-commerce nem catálogo público. O objetivo é gerar leads via formulário ou WhatsApp. Fundador: Gustavo Pedrosa, +15 anos no setor.

**CTA principal:** "Solicitar catálogo" → WhatsApp com mensagem pré-preenchida  
**Botão flutuante de WhatsApp:** presente em toda a página (canto inferior direito)

---

## Estrutura da página (ordem das seções)

1. Hero — headline + CTA
2. Credenciais — +15 anos | 5 regiões | 100% rastreável | 0 intermediários
3. Portfólio — 5 categorias (Peixes, Camarões, Moluscos, Crustáceos, Iguarias)
4. O que fazemos — 3 pilares de curadoria
5. Processo — 4 passos
6. Clientes — logos placeholder (a preencher)
7. Origem — história do Gustavo
8. CTA final
9. Formulário de contato

---

## Identidade visual

**Fonte:** Futura PT via Adobe Fonts  
```html
<link rel="stylesheet" href="https://use.typekit.net/kdl2ihv.css">
font-family: futura-pt, "Century Gothic", "Trebuchet MS", sans-serif;
```

**Cores:**
```
Cream     #FFFAF0  — background padrão, texto sobre escuro
Navy      #1A3B6B  — institucional, CTA, ilustrações curadoria
Red       #852824  — ação/urgência
Brown     #5E3C20  — texto sobre fundo claro
Sky       #AFC1CB  — suporte, cards
Wine      #4C1C12  — fundos premium escuros
Terracota #A45E37  — accents
Yellow    #EFA625  — selos, números de impacto
```

**Tipografia fluid (clamp):** Display 56–96px (800) → Body 16px (400). Ver `identidade-visual.md` para a escala completa.

---

## Assets SVG (`svgs/`)

**Logos (3 versões):**
- `Logo_Azul.svg` — sobre fundo claro (cream)
- `Logo_Offwhite.svg` — sobre fundo escuro (navy/wine)
- `Logo_Preto.svg` — impressão

**Selos (3):** `selo-curadoria de pescados.svg` | `selo-produtobrasileiro.svg` | `selo-qualidade-premium.svg`  
Todos em cream+navy. Melhor sobre fundos neutros.

**Silhuetas (10 espécies):** `pirarucu.svg`, `salmao.svg`, `bacalhau.svg`, `tilapia.svg`, `atum.svg`, `peixe.svg`, `camarao.svg`, `polvo.svg`, `lagosta.svg`, `carangueijo.svg`  
Fill hardcoded em cream `#fffaf0` — projetadas para **fundo escuro** (navy/wine).

**Curadoria cards (6):** `curadoria-pirarucu.svg`, `curadoria-camarao.svg`, `curadoria-carangueijo.svg`, `curadoria-polvo.svg`, `curadoria-ovas.svg`, `curadoria-lagosta.svg`  
Em navy — projetadas para **fundo claro** (cream). Usam `xlink` — incluir SVG inline completo.

---

## Documentos de referência

| Arquivo | Conteúdo |
|---|---|
| `Briefing.md` | Briefing completo: empresa, público, diferenciais, estrutura, formulário |
| `identidade-visual.md` | Sistema tipográfico, paleta, catálogo de SVGs, tokens CSS, cheat sheet |
| `copy-final.md` | Texto final de todas as seções (hero, credenciais, portfólio, processo, origem, CTA, formulário) |
| `copy - lp foz.md` | Versão anterior da copy (rascunho) |

---

## Decisões de design

- Seções alternam fundo escuro (navy/wine) e claro (cream) para ritmo visual
- Tipografia display em peso leve (300) nos títulos grandes = elegância intencional — não usar Bold nos heroes
- Credenciais sem ícone — austeridade é proposital
- Formulário mínimo: não pedir CNPJ neste momento, objetivo é iniciar conversa
- Fotos: produto em contexto de cozinha profissional, não banco de imagem óbvio; foto do Gustavo deve ser humana, não corporativa

## O que este site não é

- Não é e-commerce — sem carrinho ou preço listado
- Não atende pessoa física — exclusivo para foodservice
- O catálogo completo é enviado via WhatsApp após contato
