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

**Pendências desta feature (para a etapa de execução):**
- Modelo de disparo: da ação endereçada pelo motor para o rascunho de conteúdo.
- Grau de automação da interface (quase automático — definir os pontos de revisão humana).
- Formato de saída do conteúdo por tipo de motor de resposta.

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
