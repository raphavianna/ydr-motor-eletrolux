# Blueprint consolidado: motor de insights culturais e comportamentais

Documento de conhecimento do Projeto de operação diária no Claude.ai. Versão: v1.

Consolida o blueprint da etapa 1 (v2) e a arquitetura aprovada na etapa 2 do motor. Descreve a função, suas responsabilidades e seus frameworks. Não carrega escopo de piloto nem decisão específica de cliente: esse material vive no repositório do ambiente Code e evolui por lá.

---

## Visão geral

Plataforma de inteligência cultural e comportamental para uma agência de comunicação atuando na América Latina. Opera como motor cíclico, estruturado e vivo, nunca linear: captura, analisa e transforma em insight acionável a cultura e a jornada de comportamento e consumo dos consumidores das marcas-clientes, em seus territórios.

A função existe em dois ambientes complementares:

| Ambiente | Papel |
|---|---|
| Claude Code | Trabalho complexo e recorrente: base versionada, ingestão de dados de fontes, scripts, modelagem e publicação de painel |
| Claude.ai (este Projeto) | Operação diária: apresentações, pautas, textos, fluxos, cronogramas, radares, briefs, estruturas de relatório, análises pontuais e handoffs |

## Marcas-clientes

| Marca | Segmento |
|---|---|
| iFood | Delivery e fintechs |
| Eletrolux | Eletrodomésticos, principalmente linha branca |
| RD (rede de farmácias) | Varejo de saúde, health & beauty |
| MRV | Construção de moradia popular |

Cada marca é lida em seus próprios territórios, com termos e categorias no idioma local. Nenhuma tradução ou normalização automática entre territórios: cada território mantém sua própria lista de termos.

## Ciclo do motor, cinco estados

Sinal bruto → Insight validado → Ação recomendada → Ação tomada → Resultado medido. O resultado medido volta como novo sinal bruto e reabre a captura.

| # | Estado | Descrição |
|---|---|---|
| 1 | Sinal bruto | Dado capturado, ainda sem validação |
| 2 | Insight validado | Sinal que passou pelo critério de três filtros |
| 3 | Ação recomendada | Insight com pelo menos uma ação associada |
| 4 | Ação tomada | A marca ou a agência executou a ação |
| 5 | Resultado medido | Efeito da ação, que volta como novo sinal |

A base de termos, tendências e insights é versionada, nunca sobrescrita: cada termo carrega histórico de volumetria por período, cada insight carrega histórico de estado. A mesma disciplina vale para documentos e entregas da função: iteração gera versão nova, a anterior fica como histórico.

## Hierarquia de escopo, leitura e ação (versão de trabalho v1)

Escopo, do mais amplo ao mais específico: marca e concorrentes → territórios e ativos → creators → consumidores.

Leitura, aplicada sobre o escopo: cultura e tendências, e jornada de comportamento e consumo. As duas se sobrepõem na origem do dado, não são tratadas em paralelo isolado; a interseção das duas é onde o dado é gerado, antes de qualquer captura. O cruzamento profundo das duas leituras fica reservado à cadência mensal.

Ponto de virada: insight validado, o mesmo estado 2 do ciclo.

Ação, lista aberta: comunicação, conteúdo, interação, produto, mídia, stunt PR, entre outras. Interação reúne marca, engajamento, lead e venda como tipos de resultado, não como estágio fixo.

Fechamento do ciclo: o resultado medido realimenta o topo, marca, território e consumidor, reabrindo a captura.

### Duas lentes de leitura

- Cultura e tendências: o que está se movendo no território, independente de intenção de compra.
- Jornada de comportamento e consumo: onde o consumidor está no funil (pré-consideração, consideração, decisão, pós-compra) e o motivo por trás da escolha.

### Pontos de atenção da hierarquia v1

A hierarquia é versão de trabalho, não estrutura definitiva. Questões em aberto que não invalidam seu uso: a posição de tendência no eixo de escopo pode subordinar cultura ao consumidor; a jornada de funil ainda não tem posição explícita própria; as fontes não têm mapeamento formal contra cada camada; concorrentes no mesmo nível de marca dobram a superfície de observação.

## Seis pilares de fonte de dado

Por disciplina:

| Disciplina | Fontes |
|---|---|
| Social | Social listening, social intelligence, Meta Ads Library |
| Search | Semrush + Gemini, Google Trends |
| Web & AI | Webscraping multi-IA (Perplexity, ChatGPT, Gemini, outros), motores de IA (share of answer) |

O que cada ferramenta coleta:

| Ferramenta | Coleta |
|---|---|
| Social listening | Menções e sentimentos, marca, território e concorrente |
| Social intelligence | Creators em tendência e o conteúdo que produzem |
| Meta Ads Library | Criativos de referência por objetivo, indústria e território |
| Semrush + Gemini | Termos, palavras-chave e volumetrias, com deltas entre períodos |
| Google Trends | Picos e vales de busca por território |
| Webscraping multi-IA | Notícias e conteúdos; reviews e avaliações |
| Motores de IA | Respostas de prompts sobre a marca (share of answer) |

Social intelligence cobre três segmentos de creator: mainstream (alcance amplo, tendência de território ou nacional), líderes de comunidade e território (alcance local ou de nicho, autoridade dentro de um grupo) e creators de conversão/UGC (conteúdo orientado a performance, depoimento ou uso de produto). A diferença frente a social listening é o objeto de captura: listening rastreia a menção; social intelligence rastreia o creator como unidade, independente de o conteúdo citar a marca.

Stack de ferramentas por grupo: Social (Brandwatch, CreatorIQ, Influencity, TikTok Creative Center, Meta Ads Library) · Search (Semrush, Gemini, Google Trends) · Web & AI (Perplexity, ChatGPT, Gemini, Similarweb) · Integração e interação (Claude AI/Code) · Output (data viz e report).

## Critério de três filtros

Um sinal só sobe a insight compartilhável depois de passar, nesta ordem, por:

1. Magnitude do delta: desvio relevante frente ao período anterior, não ruído normal.
2. Confirmação cruzada: duas ou mais fontes na mesma direção. Fonte isolada fica como observação, não vira insight.
3. Ação disponível: existe pelo menos uma ação possível associada. É etapa posterior à validação, não pré-requisito dela.

A mesma lógica de confirmação cruzada vale para decisões de estrutura, como definir concorrentes oficiais de uma marca: um nome só entra quando aparece em pelo menos dois cruzamentos de fonte independentes, para um outlier de fonte única não virar decisão oficial.

## Cadência de output

| Cadência | Conteúdo | Audiência | Formato |
|---|---|---|---|
| Diário | Picos e quedas das últimas 24h, disparado por relevância do tema, não por calendário fixo | Mídia e performance, PR de resposta rápida, community management | Radar curto, 3 a 5 linhas |
| Semanal | Deltas da semana, leitura de tendência, status dos insights em ação, retorno das ações da semana anterior | Planejamento, criação, mídia, atendimento e cliente | Brief estruturado, top 3 a 5 insights com ação e seção de retorno |
| Mensal | Leitura de cultura e jornada, padrão cross-marca quando fizer sentido, resultado medido do mês anterior | Liderança da agência, marketing e C-level da marca | Relatório executivo |

O output semanal e o mensal sempre trazem seção de retorno, o que virou ação e qual foi o resultado medido, nunca só insight novo.

O relatório mensal tem duas versões a partir da mesma base de insight: uma interna de conta (com seção de retorno específica da conta) e uma de mercado (sem dado sensível de conta, foco em leitura de indústria e tendência). A regra do que pode sair da conta e virar conteúdo de mercado é decisão de governança de dado ainda em aberto; enquanto não fechar, a versão de mercado só carrega leitura de indústria já pública ou aprovada.

## O que o motor entrega, por frente

- Search: quanto da demanda a marca já puxa e quanto está em disputa genérica; qual marca concentra demanda por tipo de intenção; onde a marca ganha ou perde terreno para o concorrente, a tempo de agir.
- Social: espaço de conversa frente ao concorrente por território; se o volume é saudável ou custa reputação; se nasce do consumidor ou de creator pago.
- Reviews: nota média e volume de marca e concorrente no mesmo território; motivo recorrente da nota baixa; alerta antecipado antes de a reclamação virar crise.
- Share of answer (IA): se e como a marca aparece quando perguntam à IA sobre a categoria; comparação direta com o concorrente; qual fonte a IA cita.
- Conteúdo em tempo real: gatilho de resposta rápida dentro da janela relevante; território ou formato com tração orgânica comprovada; gap de mensagem entre marca e concorrente.
- Cortes: ângulo de comunicação testado por sinal real antes da produção; segmentação por consumidor, creator ou território; decisão por dado.
- Conteúdo e interação: pauta pronta direto do sinal validado; prioridade por magnitude do delta, não por ordem de chegada; gatilho de interação como parte da entrega.
- Editorias AI FIT (GEO): linha editorial pensada para ser citada pela IA, não só lida por gente; formato ajustado ao que os motores de resposta processam melhor; mesma disciplina de atualização pelos três filtros.

Todas as frentes convergem para o eixo de ação da hierarquia.

## Taxonomia de intenção de busca

| Etapa | Intenção |
|---|---|
| Descoberta | O que é, para que serve |
| Conversão | Comprar, preço, onde comprar |
| Atendimento | Cancelar, reclamação, suporte |

## Pendências estruturais da função

Registradas para que nenhuma entrega as trate como resolvidas:

- Nome exato da segunda ferramenta de social listening, além do Brandwatch.
- Critério objetivo de segmentação dos três tipos de creator do pilar social intelligence.
- Status de integração (API ou manual) de CreatorIQ, Influencity e TikTok Creative Center.
- Regra de governança do que pode sair da conta na versão de mercado do relatório mensal.
- Tradução de "magnitude relevante" e "confirmação cruzada" em regra prática por fonte e por marca.
- Mapeamento formal de cada fonte contra as camadas da hierarquia de escopo e leitura.
