# Blueprint — Motor de Insights Culturais e Comportamentais (v2)

Documento de conhecimento da etapa 1, revisado após rodada de crítica construtiva. Substitui a v1 como referência principal; a v1 fica como histórico da primeira versão. Anexe esta versão junto do system prompt v2 do Projeto.

## Visão geral

Plataforma de inteligência cultural e comportamental para uma agência de comunicação atuando na América Latina. Opera como um motor cíclico, estruturado e vivo — não linear — que captura, analisa e transforma em insights acionáveis a cultura e a jornada de comportamento e consumo dos consumidores de quatro marcas-clientes em seus territórios.

Fase atual: estruturação no Claude.ai, com documentação, provas de conceito e apresentações a partir da etapa 2. Migração planejada para Claude Code quando as bases, os termos e as marcas estiverem maduros.

## Marcas-clientes e territórios

| Marca | Segmento |
|---|---|
| iFood | Delivery e fintechs |
| Eletrolux | Eletrodomésticos, principalmente linha branca |
| RD (rede de farmácias) | Varejo de saúde, health & beauty |
| MRV | Construção de moradia popular |

## Duas lentes de leitura

- **Cultura e tendências.** O que está se movendo no território, independente de intenção de compra.
- **Jornada de comportamento e consumo.** Onde o consumidor está no funil (pré-consideração, consideração, decisão, pós-compra) e o motivo por trás da escolha.

As duas lentes são tratadas separadamente na leitura mensal, que é onde cultura e jornada se cruzam com mais profundidade.

## Fontes de dados e papel de cada uma

**1. Semrush + Gemini.** Base viva de termos, palavras-chave, territórios e etapa de funil, com volumetria, novos termos, variações e deltas entre períodos. Sem integração via API nesta fase: estimativas, volumetria e quality score feitos manualmente entre Claude e Semrush.

**2. Google Trends.** Dados mais frescos por território, para captar picos e quedas dia a dia ou semana a semana. Depende da mesma base de palavras-chave, com filtros por território.

**3. Social listening.** Menções de cada marca, territórios e concorrentes, identificando picos e quedas dia a dia ou semana a semana, em tom positivo e negativo. Integrações previstas: Brandwatch e uma segunda ferramenta ainda a confirmar. Complementar com observação direta em Meta, TikTok e X.

**4. Webscraping via Perplexity.** Motor de coleta de publicações relacionadas a marcas, concorrentes e territórios.

**5. Meta Ads Library.** Benchmarking de criativos best-in-class por objetivo, indústria e território. Tendências internacionais ajudam a antecipar tendências locais.

## Ciclo do insight

O motor fecha um ciclo, não uma linha reta:

**Captura → Insight → Ação → Resultado da ação → Captura de novo.**

Toda ação tomada a partir de um insight gera um dado de retorno (performance, novo volume de busca, nova menção), que realimenta a próxima captura.

Estados de um insight, sempre rastreados:

| # | Estado | Descrição |
|---|---|---|
| 1 | Sinal bruto | Dado capturado, ainda sem validação |
| 2 | Insight validado | Sinal que passou pelos critérios de validação |
| 3 | Ação recomendada | Insight com pelo menos uma ação associada |
| 4 | Ação tomada | A marca ou a agência executou a ação |
| 5 | Resultado medido | Efeito da ação, que volta como novo sinal |

A base de termos, tendências e insights é versionada, nunca sobrescrita: cada termo carrega histórico de volumetria por período, cada insight carrega histórico de estado.

## Critério de insight compartilhável

Antes de um sinal virar insight, ele passa por três filtros, nesta ordem:

1. Magnitude do delta — desvio relevante frente ao período anterior, não ruído normal.
2. Confirmação cruzada — duas ou mais fontes na mesma direção. Fonte isolada fica como observação, não vira insight.
3. Ação disponível — existe pelo menos uma ação possível associada.

## Output recorrente

| Cadência | Conteúdo | Audiência | Formato |
|---|---|---|---|
| Diário | Picos e quedas das últimas 24h, disparado só quando o tema for relevante | Mídia/performance, PR de resposta rápida, community management | Radar curto, 3 a 5 linhas |
| Semanal | Consolidação dos deltas da semana, leitura de tendência, status dos insights em ação, retorno das ações da semana anterior | Planejamento, criação, mídia, atendimento e cliente | Brief estruturado, top 3 a 5 insights com ação e seção de retorno |
| Mensal | Leitura de cultura e jornada, padrão cross-marca quando fizer sentido, resultado medido do mês anterior | Liderança da agência, marketing e C-level da marca | Relatório executivo |

O output semanal e o mensal sempre trazem uma seção de retorno — o que virou ação e qual foi o resultado medido —, nunca só insight novo.

## Fluxo de cinco etapas

| # | Etapa | Status |
|---|---|---|
| 1 | Captura e estruturação do pedido em prompt | Concluída |
| 2 | Estrutura e fluxo de trabalho ancorados para migração ao Claude Code (documentações, apresentações, arquivos) | Aguardando aprovação |
| 3 | Fontes, fluxos e métricas, incluindo setup técnico de conectores (autenticação e mapeamento de cada fonte) | Aguardando aprovação |
| 4 | Business case com dados reais, com checkpoint de validação junto ao time de mídia/planejamento da marca antes de fechar, e migração para Claude Code | Aguardando aprovação |
| 5 | Escala — cada nova frente aprovada reaciona a skill agente-de-prompts | Contínua |

## Tipo de insight e desdobramento

Todo insight validado aponta para pelo menos uma ação possível. A lista não é fechada: comunicação, produto, conteúdo, interação, stunt PR, mídia, entre outras que façam sentido para o caso.

## Decisões tomadas até aqui

- Apresentações iniciais só a partir da etapa 2 ou 3.
- O motor é cíclico: toda ação gera dado de retorno que realimenta a captura.
- A base é versionada, nunca sobrescrita.
- Cliente entra como audiência do output semanal.
- O output diário é disparado por relevância do tema, não por calendário fixo.
- Setup de conectores entra na etapa 3; checkpoint de validação com a marca entra na etapa 4.
- A lista de ações possíveis é aberta, não fechada.

## Pontos em aberto

- Nome exato da segunda ferramenta de social listening.
- Destino do output mensal: relatório fechado para a marca, ou também insumo de pitch de novo negócio — ainda não respondido, e muda o tom e o nível de exposição de dado no material.
- Se a etapa 4 mira retenção/expansão de conta existente ou pitch de novo negócio — mesma pendência da anterior, ainda em aberto.
- Lista final de métricas por fonte de dado, a fechar na etapa 3.
- Definição de filtros e territórios exatos por marca (nacional, estado, capital).

## Papel da skill agente-de-prompts no projeto

Toda vez que uma etapa for aprovada, a skill agente-de-prompts é ativada para gerar o prompt daquela etapa, seguindo o mesmo padrão de entrega: prompt final, racional técnico, variáveis, parâmetros quando aplicável e critério de teste. Este documento e o system prompt do Projeto são a âncora consultada antes de cada nova etapa.
