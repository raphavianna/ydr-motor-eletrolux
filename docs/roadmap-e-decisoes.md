# Roadmap e decisões — piloto Eletrolux (registro vivo)

Complemento ao documento-mãe (`briefing-tecnico-piloto-eletrolux.md`). Registra decisões e features acordadas ao longo da execução que ainda não estavam no briefing. Não substitui o briefing; ancora o que foi decidido depois dele.

---

## Feature ancorada — Geração de conteúdo AI-native no painel (pilar GEO)

**Status:** ancorada, execução em etapa posterior (depois do painel base). Não construir agora.

**O que é:** o painel passa a incluir uma feature para **gerar conteúdo AI-native diretamente a partir das ações que o motor endereça**. Ou seja: o motor identifica a ação (ex.: um gap de share of answer numa categoria) e o painel oferece, ali mesmo, a criação do conteúdo correspondente — de forma **quase automática**, sem sair para outra ferramenta.

**Onde aparece:**
- **No painel:** uma interface de criação desses conteúdos, acoplada ao eixo de ação (hierarquia §2.2 do briefing) e à leitura de share of answer / AI.
- **Na apresentação:** deve constar nos **slides sequenciais** do deck, como parte da narrativa do produto (a produção do deck é etapa separada).

**Por que faz sentido no racional:** é a materialização operacional da editoria **AI FIT (GEO)** já prevista no briefing §2.6 — conteúdo pensado para ser citado pela IA, agora gerado dentro do próprio fluxo do motor, fechando o ciclo insight → ação → conteúdo sem handoff manual.

**Terminologia — AI e GEO (dois pilares da leitura de IA):**
- **AI** = medição: onde a marca está na resposta de IA (share of answer, visibilidade por categoria, menções vs. concorrente).
- **GEO** = ação (Generative Engine Optimization): onde e como ganhar a resposta — os gaps viram pauta de conteúdo AI-native gerado no painel.

**Referência de interface:** o gerador de conteúdo do Semrush (tipo ContentShake / SEO Content — parâmetros estruturados, score "Ready to rank", Title Tag e Meta Description). O painel replica essa tela **internamente**, com Semrush no backend, mas **alimentada pelo drill-down do motor** — não é o usuário digitando um tema do zero, é o motor apontando o quê criar.

### Fluxo: da leitura de IA à criação de conteúdo (drill-down)

1. **Leitura AI** — share of answer + visibilidade por categoria mostram onde a marca tem espaço de crescimento (ex.: *Máquinas de Lavar e Secar*, visibilidade 49; no tópico, Midea lidera 79 vs. Electrolux 48).
2. **Drill-down GEO** — ao clicar na categoria/gap, o painel abre os **tópicos específicos** que devem receber conteúdo (de gap_topics/brand_topics cruzado com a base de termos daquele tópico), rankeados por volume × gap de visibilidade.
3. **Seleção de tópicos** — o usuário marca os tópicos-pauta.
4. **Brief automático** — o painel monta o brief espelhando a nossa estrutura (território, idioma local, keywords validadas do tópico, categoria/lente/funil).
5. **Geração AI-native** — Semrush no back gera o conteúdo com título, meta description e score de prontidão para ser citado/rankeado.
6. **Fechamento de ciclo** — conteúdo publicado = ação tomada → resultado medido → realimenta a leitura de share of answer (ciclo §2.1). A próxima leitura mostra se a visibilidade subiu.

### De-para: parâmetros do gerador ↔ nossa estrutura

| Parâmetro (gerador Semrush) | Nossa estrutura |
|---|---|
| Location | território (BR / MX / AR / CO) |
| Language | idioma local (§5.5) — pt-BR, es-MX… |
| Keywords | termos validados do tópico (base madura, com volume real) |
| Title / Topic | tópico/gap selecionado no drill-down |
| Content type | derivado da lente/funil (guia→descoberta, comparativo→consideração, "não liga"→atendimento) |
| Tone / Readability | filtro editorial da marca |
| SEO-booster / "Ready to rank" | critério de prontidão AI-FIT/GEO |

**Pendências desta feature (para a etapa de execução):**
- Modelo de disparo: da ação endereçada pelo motor para o rascunho de conteúdo.
- Grau de automação da interface (quase automático — definir os pontos de revisão humana).
- Formato de saída do conteúdo por tipo de motor de resposta.
- Regra de ranqueamento dos tópicos no drill-down (peso de volume vs. gap de visibilidade).
- API do gerador Semrush no backend vs. modelo manual, alinhado ao §5.4.

---

## Módulo AI/GEO — ativo no piloto

Decisão: o módulo de share of answer / IA entra **ativo** no piloto (antes era etapa posterior no briefing). Motivo: o próprio export de Semrush (e Similarweb, canal Gen AI) já traz a camada de performance de IA, sem custo de fonte nova. A camada de IA é **atributo do termo/tópico**, não uma fonte separada.

Fontes de IA já em uso:
- Semrush **AI tracking** (gap_topics, brand_topics): share of answer por tópico, menção por marca, visibilidade da Electrolux por categoria.
- Semrush organic (SERP Features `AI Overview`, Position Type `AI overview`): presença e citação em AI Overview por keyword.
- Similarweb canal **Gen AI**: tráfego real vindo de IA generativa, série mensal.

---

## Decisões de dado e estrutura registradas nesta rodada

- **Parametrização por segmento** (não por tags soltas): `produto_puro`, `produto_marca`, `marca_pura`, `marca_funil`, `generico` — em colunas explícitas, com `Marca (tipo/nome)` e `Funil` ortogonal.
- **Lente jornada/comportamento**: além de produto e marca, a base carrega termos de cultura/uso — `receita`, `duvida`, `problema`, `comparativo` — que validaram alto volume real (ex.: receitas de air fryer/microondas).
- **Expansão = geração de candidatos novos** (sem volume) para rodar no Semrush e ancorar com demanda real; candidatos com volume 0 são descartados (filtro por demanda).
- **De-para BR→MX**: tradução local es-MX (estufa, refrigerador, freidora de aire, minisplit), métricas locais (pies, toneladas, pulgadas) e marcas locais (Mabe, Whirlpool, Acros/IEM, Mirage, Calorex, Oster, Koblenz…).
- **Idioma local por território** mantido (§5.5): nenhuma normalização automática entre territórios; o de-para gera sementes, validadas com dado real de cada país.
- **Filtro de ruído**: termos em inglês (blog internacional) e off-topic (jogos, retail genérico) filtrados; no gap_topics de IA, tópicos de varejo/genéricos separados da leitura por categoria.

---

## Pendências de escopo em aberto

- Tratar **Mabe/Acros/IEM** como concorrentes separados ou como bloco do grupo Mabe (afeta a leitura de share por marca).
- Persistir a base madura no repositório (`data/master`) no formato versionado (§5.3) — a decidir quando fechar BR + MX.
- Recalcular o share of answer **apenas sobre tópicos de categoria de eletrodoméstico** (leitura mais fiel à disputa real).
