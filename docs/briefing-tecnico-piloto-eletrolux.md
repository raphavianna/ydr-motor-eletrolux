# Briefing técnico: motor de insights culturais e comportamentais — piloto Eletrolux LatAm

Documento-mãe para a migração ao Claude Code. Consolida a arquitetura aprovada na etapa 2 (blueprint, frameworks e apresentação final) mais o escopo específico do piloto. Status: rascunho para certificação. Nenhuma etapa técnica roda antes deste documento ser aprovado.

---

## 1. Propósito e contexto

Plataforma de inteligência cultural e comportamental para uma agência de comunicação atuando na América Latina. Opera como motor cíclico, não linear: captura, analisa e transforma em insight acionável a cultura e a jornada de comportamento e consumo dos consumidores de marcas-cliente, em seus territórios.

Este piloto testa a arquitetura completa com um cliente e um recorte geográfico real, antes de generalizar para as demais marcas do portfólio (iFood, RD, MRV).

---

## 2. Arquitetura aprovada (etapa 2, versão de trabalho v1)

### 2.1 Ciclo do motor, cinco estados

Sinal bruto → Insight validado → Ação recomendada → Ação tomada → Resultado medido → o resultado medido volta como novo sinal bruto, reabrindo o ciclo. A base de termos e insights é versionada, nunca sobrescrita: cada termo carrega histórico de volumetria por período, cada insight carrega histórico de estado.

### 2.2 Hierarquia de escopo, leitura e ação

**Escopo**, do mais amplo ao mais específico: marca e concorrentes → territórios e ativos → creators → consumidores.

**Leitura**, aplicada sobre o escopo: cultura e tendências e jornada de comportamento e consumo se sobrepõem na origem do dado, não são tratadas em paralelo isolado. A interseção das duas é onde o dado é gerado, antes de qualquer captura.

**Ponto de virada**: insight validado.

**Ação**, lista aberta: comunicação, conteúdo, interação, produto, mídia, stunt PR, entre outras. Interação reúne marca, engajamento, lead e venda como tipos de resultado, não como estágio fixo.

**Fechamento do ciclo**: o resultado medido realimenta o topo, marca, território e consumidor, reabrindo a captura.

### 2.3 Fontes de dado, por disciplina

| Disciplina | Fontes |
|---|---|
| Social | Social listening, social intelligence, Meta Ads Library |
| Search | Semrush + Gemini, Google Trends |
| Web & AI | Webscraping multi-IA (Perplexity, ChatGPT, Gemini, outros), motores de IA (share of answer) |

### 2.4 O que cada ferramenta coleta

| Ferramenta | Coleta |
|---|---|
| Social listening | Menções e sentimentos |
| Social intelligence | Creators em tendência |
| Meta Ads Library | Criativos de referência |
| Semrush + Gemini | Termos e volumetrias |
| Google Trends | Picos e vales de busca |
| Webscraping multi-IA | Notícias e conteúdos; reviews e avaliações |
| Motores de IA | Respostas de prompts sobre a marca |

Tudo isso alimenta a captura, que o motor processa pelo critério de três filtros abaixo.

### 2.5 Critério de três filtros

Sinal → **Magnitude do delta** (desvio relevante frente ao período anterior) → **Confirmação cruzada** (duas ou mais fontes na mesma direção; fonte isolada vira observação, não insight) → **Insight validado** → **Ação disponível** (etapa posterior à validação, não pré-requisito dela) → Ação recomendada.

### 2.6 O que o motor entrega, oportunidades estratégicas

**Search**
- Quanto da demanda já é puxada pela marca, e quanto ainda está em disputa genérica, por produto
- Qual marca concentra a demanda em termos de conversão, de descoberta ou de atendimento, o raio-x da força de cada marca por tipo de intenção
- Onde a marca ganha ou perde terreno para o concorrente, a tempo de agir antes do resultado de trimestre

**Social**
- Quanto espaço de conversa a marca ocupa frente ao concorrente, território a território
- Se esse espaço é saudável, ou é volume às custas de reputação
- Se o volume nasce do consumidor ou de creator pago, para calibrar investimento em mídia

**Reviews**
- Nota média e volume, marca e concorrente, no mesmo território
- Motivo recorrente por trás da nota baixa
- Alerta antecipado, antes que a reclamação vire crise de mídia

**Share of answer, IA**
- Se a marca aparece, e como, quando perguntam à IA sobre a categoria
- Comparação direta com o concorrente na mesma pergunta
- Qual fonte a IA está citando para responder sobre a marca

**Conteúdo, tempo real**
- Gatilho de resposta rápida, dentro da janela que ainda importa
- Território ou formato com tração orgânica comprovada
- Gap de mensagem entre marca e concorrente

**Cortes**
- Ângulo de comunicação testado por sinal real, antes da produção
- Segmentação por consumidor, creator ou território
- Base de decisão por dado, não por opinião

**Conteúdo e interação**
- Pauta pronta, direto do sinal validado, sem esperar briefing
- Prioridade por magnitude do delta, não por ordem de chegada
- Gatilho de interação, comentário e engajamento, como parte da entrega

**Editorias AI FIT (GEO)**
- Linha editorial pensada pra ser citada pela IA, não só lida por gente
- Formato ajustado ao que os motores de resposta processam melhor
- Mesma disciplina de atualização, pelo critério de três filtros

Todas as oportunidades acima convergem para o eixo de ação da hierarquia (2.2).

### 2.7 Stack de ferramentas e conectores

| Grupo | Ferramentas |
|---|---|
| Social | Brandwatch, CreatorIQ, Influencity, TikTok Creative Center, Meta Ads Library |
| Search | Semrush, Gemini, Google Trends |
| Web & AI | Perplexity, ChatGPT, Gemini, Similarweb |
| Integração e interação | Claude AI/Code |
| Output | Data viz e report |

### 2.8 Cadência de output

Diário (radar curto, disparado por relevância) · Semanal (brief estruturado, com seção de retorno) · Mensal (relatório executivo, com seção de retorno).

---

## 3. Escopo do piloto Eletrolux

### 3.1 Marca e territórios
Eletrolux, quatro territórios: Brasil, México, Argentina, Colômbia.

### 3.2 Sites de referência, DTC e-commerce
- Brasil: https://loja.electrolux.com.br/
- México: https://www.electrolux.com.mx/
- Argentina: https://www.tienda.electrolux.com.ar/
- Colômbia: https://www.electrolux.com.co/

Servem de base para o primeiro levantamento de produto, categoria e termo por território.

### 3.3 Ferramentas do piloto
Semrush, Similarweb e Google Trends, alimentando o modelo com dado real. Uso via conector MCP ao vivo, quando disponível no ambiente de execução.

O uso ao vivo se limita às etapas de ingestão (2 a 6), dentro do Code. O painel publicado (etapa 10) lê apenas dado já versionado na base mestre, sem chamada de API em tempo de execução. Isso resolve a compatibilidade com publicação estática no Netlify: nenhuma dependência de backend vivo no painel final.

### 3.4 Concorrentes por território
Em aberto. A identificar na etapa 2, categoria linha branca e pequenos eletrodomésticos, por território.

Metodologia: top domínios por participação de tráfego na categoria (Similarweb, por território), cruzado com top domínios por visibilidade de busca na mesma categoria (Semrush, por território). Um domínio só entra na base de concorrentes se aparecer nos dois cruzamentos — mesma lógica de confirmação cruzada do critério de três filtros (item 2.5), para não deixar um outlier de fonte única virar concorrente oficial.

### 3.5 Repositório de destino
https://github.com/raphavianna/ydr-motor-eletrolux — status de acesso a confirmar antes da etapa 1 técnica.

---

## 4. Fluxo de migração, dez etapas

Cada etapa recebe seu próprio prompt técnico, gerado e revisado via skill agente-de-prompts, uma de cada vez. Nenhuma etapa começa antes da anterior estar rodada e validada.

1. Setup do projeto e repositório
2. Estruturação da base mestre v1: marca, concorrentes, produtos, termos e palavras-chave, por categoria/etapa de funil e por mês
3. Ingestão de reports Similarweb e Semrush, priorizando quebra mensal
4. Revisão do modelo da base
5. Expansão de termos, palavras-chave e outros dados gerados nos reports
6. Definição das abas do painel, "search intel", a partir do que o motor entrega (item 2.6 deste briefing) e da base já madura nesse ponto do fluxo
7. Primeira modelagem do painel piloto, com as abas definidas na etapa 6
8. Ajustes
9. Refino de UX via Claude Design
10. Publicação, Netlify

### Nota sobre a etapa 6
A definição das abas não é assumida neste briefing. Ela acontece dentro do próprio fluxo do Code, na etapa 6, quando a base mestre já estiver madura o bastante para informar a decisão. O item 2.6 deste documento é o ponto de partida, não a resposta pronta.

---

## 5. Convenções técnicas

### 5.1 Estrutura de pasta
`/data/raw/{fonte}/{territorio}/{ano-mes}/` (reports originais, sem tratamento) · `/data/master/` (base mestre versionada) · `/app/` (painel) · `/docs/` (documentação).

### 5.2 Schema da base mestre

**Registro de termo**
- `term_id`: identificador estável (hash de termo + marca + território), mantém identidade entre atualizações
- `term`, `brand`, `is_own_brand` (booleano)
- `product_category`
- `funnel_stage`: descoberta | conversão | atendimento (taxonomia em 5.6)
- `territory`: BR | MX | AR | CO
- `month`: AAAA-MM
- `search_volume`, `volume_delta_mom` (variação frente ao mês anterior)
- `source`: semrush | similarweb | trends
- `ingested_at`, `version`

**Registro de concorrente**
- `competitor_id`, `competitor_name`, `territory`, `category`, `identified_method` (metodologia em 3.4)

### 5.3 Formato e versionamento
Um arquivo JSON Lines por lote de ingestão, nomeado por fonte, território e data, nunca editado depois de criado. Uma view consolidada "latest" é gerada por script a partir do histórico completo, para consumo do painel. A view pode ser recriada a qualquer momento; o histórico bruto, nunca.

### 5.4 Credencial e acesso
Chave de API de Semrush e Similarweb gerenciada pelo conector MCP do ambiente Code, nunca gravada em texto no repositório. Se o conector não estiver disponível na etapa, a etapa para e reporta, em vez de simular dado.

### 5.5 Idioma, moeda e território
Termo e categoria capturados no idioma local de cada território, pt-BR, es-MX, es-AR, es-CO. Nenhuma tradução ou normalização automática entre territórios nesta fase: cada território mantém sua própria lista de termos.

### 5.6 Taxonomia de etapa de funil
Descoberta (o que é, para que serve) · Conversão (comprar, preço, onde comprar) · Atendimento (cancelar, reclamação, suporte). Mesma taxonomia usada no item 2.6 deste briefing, agora formalizada como campo de dado.

---

### 5.7 Interface
Todo o material é tratado como atemporal: sem marcação de "novo" em qualquer elemento de interface do painel.

---

## 6. Pendências conhecidas, herdadas da etapa 2

- Nome exato da segunda ferramenta de social listening, além do Brandwatch.
- Status de integração, via API ou manual, de CreatorIQ, Influencity e TikTok Creative Center.
- Critério de segmentação dos três tipos de creator do pilar social intelligence.
- Concorrentes por território para o piloto Eletrolux (item 3.4 acima).

Nenhuma dessas pendências bloqueia o início da etapa 1 técnica.
