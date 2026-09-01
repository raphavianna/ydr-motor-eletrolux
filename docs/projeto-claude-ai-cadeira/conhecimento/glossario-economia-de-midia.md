# Glossário de economia de mídia

Documento de conhecimento do Projeto de operação diária no Claude.ai. Versão: v1.

Vocabulário obrigatório da cadeira (seção 6 do dossiê), com definição de trabalho e o alerta de uso de cada termo. Serve para manter o vocabulário consistente entre entregas e para traduzir métrica de mídia em métrica de negócio. Nenhum benchmark numérico vive aqui: número entra na entrega apenas com fonte rastreável (R2).

## Custo e valor

- CAC (custo de aquisição de cliente): investimento dividido por clientes novos adquiridos. Alerta: declarar o que entra no numerador (só mídia, ou mídia mais operação) e se o denominador é cliente novo de fato ou conversão qualquer.
- LTV (lifetime value): valor que o cliente gera ao longo do relacionamento, em margem, não em receita. Alerta: LTV em receita infla a leitura; horizonte de projeção declarado.
- Relação LTV/CAC: quantas vezes o valor do cliente paga sua aquisição. Alerta: só compara operações com margem e ciclo semelhantes.
- Margem de contribuição: o que sobra da receita depois de custos variáveis. É o que define qual CAC é sustentável; sem ela, não existe meta de eficiência defensável.
- Custo de oportunidade da verba: o que o mesmo real renderia na melhor alternativa entre práticas. Toda recomendação de alocação o considera, mesmo quando implícito.

## Retorno e resposta

- ROAS: receita atribuída dividida pelo investimento no canal. Alerta: herda todos os vieses da atribuição; não é lucro e não é incrementalidade.
- ROI: retorno em margem sobre o investimento. Alerta: dizer sempre qual receita e qual custo entram na conta.
- ROI marginal: o retorno do próximo real, não a média do investido. É a medida que decide alocação (D6).
- Curva de resposta: relação entre investimento e resultado por canal. É dela que saem o ROI marginal e a saturação.
- Ponto de saturação: nível de investimento a partir do qual o retorno marginal cai de forma relevante. Sinais operacionais de proximidade: frequência crescente com entrega travada e custo subindo sem ganho de alcance.
- Adstock e meia-vida: efeito de arrasto do investimento no tempo e o prazo em que metade dele se dissipa. Saem do MMM; sem MMM, o efeito existe mas não está medido, e a leitura de janela curta o ignora.
- Venda base vs venda incremental: o que aconteceria sem o investimento contra o que o investimento adicionou. É a separação que decide verba; atribuição de plataforma não a enxerga.
- Elasticidade (a preço, a promoção, a mídia): variação percentual da venda por variação percentual do estímulo. Sem ela, não se separa efeito de comunicação de efeito de desconto.

## Participação e pressão competitiva

- Share of market: participação da marca nas vendas da categoria. Decomposto em penetração, frequência e ticket para virar diagnóstico.
- Share of voice (SOV): participação da marca na pressão de comunicação paga da categoria. Exige conjunto competitivo e fonte declarados.
- Share of spending: participação no investimento total da categoria. Leitura de pressão em dinheiro, complementar ao SOV em presença.
- ESOV (excess share of voice): SOV menos share of market. Preditor clássico de crescimento de participação; positivo tende a preceder ganho de share, negativo tende a preceder perda. Alerta: relação de tendência histórica, não garantia por categoria.
- Share of social: participação da marca no volume de conversa espontânea da categoria (P9). Contraparte não paga do SOV; sem denominador competitivo declarado, não é share.
- Share of search: participação da marca nas buscas da categoria. Proxy de demanda relativa e de disponibilidade mental; alerta: influenciado por notícia e crise, não só por preferência.
- Triângulo de share: leitura conjunta de SOV (o que compramos), share of social (a conversa que geramos) e share of market (o que vendemos). O diagnóstico está na distância entre os três (detalhe no dossiê, P9).

## Marca e memória

- Disponibilidade mental: probabilidade de a marca ser lembrada quando a categoria é acionada. Construída por alcance, distintividade e presença nos pontos de entrada.
- Disponibilidade física: estar presente e comprável onde a decisão acontece, do varejo à prateleira digital.
- Pontos de entrada de categoria: as situações que disparam a compra. Unidade de planejamento de comunicação de marca, no lugar do perfil demográfico.
- Lembrança espontânea e estimulada, consideração, preferência: os degraus de métrica de marca medidos por BHT. Movem devagar; leitura por onda, não por semana.
- Frequência efetiva: o número de exposições necessário para o efeito pretendido. Acima dele, com criativo único, começa fadiga, que aparece no engajamento antes de aparecer no custo.
- Atenção: qualidade da exposição, não só entrega. Alerta: métricas de atenção variam por fornecedor; declarar a métrica usada.

## Medição

- Atribuição e janela de atribuição: regra pela qual conversões são creditadas a exposições e o período considerado. Mudança de janela muda o número sem mudar a realidade.
- View-through: conversão creditada a impressão sem clique. Peso alto de view-through infla o crédito do canal.
- Brand lift, holdout, teste incremental, MMM: instrumentos da escada da prova (detalhe no método de prova e testes).
- Incrementalidade: a fração do resultado que não aconteceria sem a ação. É o que a palavra "funcionou" deveria significar em qualquer entrega.

## Dado e audiência

- 1P, 2P, 3P data: dado próprio, de parceiro e de terceiros. 1P rende em relacionamento e recorrência; 3P e sinal de plataforma rendem em prospecção ampla (D5).
- Lookalike: modelagem de audiência sobre semente 1P. Não é 1P; degrada com a qualidade da semente.
- CDP: plataforma que unifica o dado de cliente para segmentação e ativação. É camada de operação, não estratégia por si.
- Sobreposição de audiência: fração de base compartilhada entre creators ou canais do mesmo plano. Alcances somados sem descontá-la são ficção: entregam frequência, não alcance.
- CPM efetivo de creator: custo do creator dividido pelo alcance qualificado entregue, em milhares. Métrica primária de seleção e verba em P9, no lugar de seguidores e engajamento.

## Jornada

- Messy middle: o loop de exploração e avaliação entre gatilho e compra, sem ordem fixa. Fundamento do planejamento por momento, não por etapa de funil.
- Funil fragmentado: consequência operacional do messy middle: momentos de jornada substituem etapas lineares como unidade de plano.
- Retail media: mídia dentro do ambiente do varejista, onde disponibilidade física e mental se encontram e onde o dado de venda permite prova de incrementalidade.
