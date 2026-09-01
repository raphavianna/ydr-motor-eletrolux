# Guia de entregas: operação diária da cadeira

Documento de conhecimento do Projeto de operação diária no Claude.ai. Versão: v2 (v1 tratava a peça visual como etapa separada; a v2 define a peça final como entrega default de cada tipo).

Especificação e template de cada tipo de entrega do dia a dia da Direção Executiva de Mídia e Dados. O template é o formato de referência: os campos fixos permanecem em toda entrega do tipo; a profundidade de cada campo se adapta ao caso. Toda entrega segue o filtro editorial, as regras de dado e o padrão de insight das instruções do Projeto, abre com a célula da matriz (mandato × prática) quando for substantiva e nasce no formato final de uso declarado no tipo.

---

## 1. Plano de mídia

Quando usar: desenhar ou revisar um plano em nível executivo (apenas a base versionada e o pipeline recorrente do plano pertencem ao Code).

Formato final: documento executivo mais planilha de verba (xlsx) quando houver números, com cenários modelados em abas, não descritos em texto. Quando o plano for defendido em reunião, a apresentação em HTML sai junto (tipo 4).

Estrutura fixa:

1. Célula da matriz, pergunta que o plano responde e elo da cadeia causal pelo qual pretende agir.
2. Contexto e gargalo: por que mídia é a alavanca certa aqui (referência à tese 2.2 do dossiê).
3. Momentos da jornada cobertos, cada um com audiência, dado que a define, canal, formato, mensagem e verba.
4. Split marca vs ativação com o racional (D1 do dossiê, sempre como benchmark a validar).
5. Regras de otimização declaradas antes de começar: o que sobe, o que desce, com qual leitura e em qual janela.
6. Fatia de teste: hipótese, desenho, prazo de leitura (D4).
7. Hipótese de retorno de negócio no vocabulário de economia do dossiê. Plano sem essa seção é lista de compras.
8. Como o plano será provado: instrumento por elo, degrau da escada da prova.

Regra do tipo: verba sempre discutida em efeito marginal (D6). Sem dado de saturação, dizer isso e propor como levantá-lo.

## 2. Report e leitura de performance

Quando usar: produzir report periódico, executivo ou de campanha a partir do dado fornecido (apenas o pipeline automatizado que alimenta report recorrente pertence ao Code).

Formato final: documento executivo; quando o report for visual ou comparativo, dashboard em HTML com gráficos gerados por código a partir do dado fornecido, nunca gráfico descrito em texto.

Estrutura fixa:

1. Sumário executivo: as três leituras que importam, em prosa.
2. Resultado contra meta, com fonte de cada número.
3. Insights no padrão de cinco partes (observação, causa provável, implicação, recomendação, prova).
4. Seção de prova: em qual degrau da escada está cada afirmação de valor. Número de plataforma nunca apresentado como incrementalidade (D3).
5. Decisões tomadas no período e efeito observado.
6. Recomendações priorizadas por efeito marginal esperado.
7. Pendências e lacunas declaradas.

Regra do tipo: número sem leitura não entra (R1). Ao comparar canais de horizontes diferentes, declarar o viés contra construção de marca da janela curta.

## 3. Análise de dados colados ou anexados

Quando usar: o usuário cola um export, anexa um arquivo ou relata um dado e pede leitura.

Formato final: leitura em prosa na conversa; com arquivo anexado ou volume relevante, a análise roda em execução de código, com número calculado e método declarado. Quando a leitura merecer circular, versão em documento ou dashboard.

Estrutura fixa:

1. Classificação da pergunta: diagnóstico, previsão ou decisão (seção 7 do dossiê), porque cada tipo exige evidência diferente.
2. Leitura em prosa do que o dado mostra e do que não mostra.
3. Insights no padrão de cinco partes, com inferência marcada por grau de confiança (R3) e métrica-proxy nomeada quando houver (R4).
4. O que eu faria a seguir.

Regra do tipo: nenhum número que não esteja no dado colado. Comparação com período anterior só quando o dado anterior também estiver disponível; caso contrário, [a confirmar].

## 4. Apresentação

Quando usar: qualquer apresentação da função, interna, de cliente ou de concorrência.

Formato final: a apresentação pronta, em HTML navegável, com acabamento visual de nível de agência (hierarquia tipográfica, dado em gráfico e não em parágrafo, um ponto por slide). O roteiro slide a slide acompanha como documentação quando houver contexto de fala relevante:

```
## Slide N: [título]
Mensagem-chave: [uma frase que sustenta o slide sozinha]
Pontos de apoio: [2 a 4 itens]
Nota do apresentador: [contexto de fala, só quando houver]
```

Regras do tipo: a narrativa segue o padrão de defesa da cadeira, tese antes de dado, dado antes de recomendação, recomendação com prova e custo de estar errado; separar decisão fechada de hipótese em teste no primeiro slide em que as duas convivem; lacunas e premissas ganham slide próprio perto do fim, porque lacuna declarada na defesa joga a favor; declarar teto de slides assumido quando o pedido não fixar um. Estrutura para aprovação antes da peça só quando o usuário pedir; o default é entregar a apresentação completa e iterar sobre ela.

## 5. Pauta de reunião

Estrutura fixa:

```
Pauta · [tema] · [data] · [duração]
Objetivo: [decisão ou resultado esperado da reunião, em uma frase]
Participantes: [nomes ou papéis]

Blocos:
1. [bloco] · [min] · [decisão esperada ou "informativo"]
2. ...

Pendências entrantes: [o que chega em aberto de conversas anteriores]
Encaminhamentos: [preencher ao fim: decisão, responsável, prazo]
```

Regra do tipo: todo bloco declara se espera decisão ou é informativo. Reunião sem decisão esperada em nenhum bloco merece a pergunta: precisa ser reunião?

## 6. Cronograma

Quando usar: calendário de entregas, plano de projeto, janela de campanha, marcos de concorrência.

Estrutura fixa: etapas sequenciais numeradas, cada uma com entregável, responsável, dependência e status.

```
| # | Etapa | Entregável | Responsável | Depende de | Status |
```

Status possíveis: concluída, em andamento, aguardando aprovação, pendente. Datas só quando o usuário fornecer; sem data, ordenar por dependência. Gate de aprovação entre etapas explícito quando houver.

Formato final: tabela em markdown para consumo direto; planilha (xlsx) quando o cronograma for gerido fora da conversa ou tiver datas e responsáveis a atualizar.

## 7. Fluxo de trabalho e desenho de processo

Quando usar: desenhar ou revisar um processo da cadeira, de uma conta ou de uma rotina candidata a automação.

Estrutura fixa: estados nomeados, gatilho de entrada de cada estado, responsável e saída. Todo fluxo novo nasce como v1, com pontos de atenção listados ao fim.

Regra do tipo: quando o fluxo envolver automação, declarar o degrau na escada de autonomia (N0 a N4) e os guardrails de P10; nomear o que permanece com julgamento humano (R6). Rotina executada três vezes da mesma forma é candidata a produto: quando o desenho revelar esse padrão, apontar a transição para M4.

## 8. Textos e comunicações

Quando usar: e-mails, mensagens, resumos executivos, comunicados, respostas a cliente.

Regras do tipo: identificar audiência e objetivo antes de escrever; uma mensagem central por texto; filtro editorial integral; para e-mail, assunto proposto e um só call to action. O que é dito ao cliente é decisão humana (R6): texto para cliente sai como proposta de redação, com alternativa quando o tom for sensível.

## 9. Tese e ponto de vista

Quando usar: posicionamento da cadeira sobre um tema, uma mudança de mercado ou uma escolha de método, para uso interno, com cliente ou em concorrência.

Estrutura fixa:

1. A tese em uma frase.
2. O que sustenta: evidência disponível, com fonte, e princípio da doutrina aplicado.
3. O melhor contra-argumento e por que a tese sobrevive a ele (ou em que condição não sobrevive).
4. Implicação prática: o que muda no trabalho se a tese valer.
5. O que a derrubaria: dado ou evento que forçaria revisão.

Regra do tipo: tese sem contra-argumento examinado é opinião. Separar o que o dado mostra do que é inferência (R3).

## 10. Brief para prática

Quando usar: transformar decisão ou aprendizado em brief acionável para uma prática (criativo para P5, creator para P9, conteúdo de busca para P4, segmentação para P3).

Estrutura fixa:

```
Brief · [prática destino] · [campanha ou tema] · v1
Contexto: [de onde vem este brief: decisão, leitura ou aprendizado que o origina]
Objetivo: [o que a peça ou ação deve mover, em métrica de negócio]
Audiência e momento: [quem e em qual momento da jornada]
Território e mensagem: [ponto de entrada de categoria em disputa; o que dizer]
Restrições: [marca, jurídico, formato, prazo]
Prova: [como saberemos que funcionou, com qual métrica e leitura]
```

Regra do tipo: brief nascido de leitura de conteúdo (por exemplo, engajamento quebrado por peça) declara o contexto de comparação usado, porque engajamento só compara dentro do mesmo contexto.

## 11. Planilha e modelo de trabalho

Quando usar: a entrega é um instrumento de trabalho tabular ou de simulação. Modelo de verba e cenários, simulador de CAC sustentável por margem, base de curadoria de creators com sobreposição e CPM efetivo, calendário de investimento, controle de testes.

Formato final: arquivo xlsx com abas nomeadas, fórmulas vivas onde a lógica permitir e uma aba de premissas com fonte de cada input. Csv quando o destino for outra ferramenta.

Regras do tipo: input separado de cálculo e de resultado; premissa marcada com [a confirmar] quando faltar dado; nenhuma constante enterrada em fórmula sem estar declarada na aba de premissas.

## 12. Briefing de handoff para o Code

Quando usar: apenas quando a execução exige repositório e recorrência (base versionada, ingestão automatizada de fontes, pipeline de dado em produção, agente de operação via API, engenharia de produto). Antes do handoff, produza aqui tudo o que o ambiente sustenta: a análise, o desenho, o modelo, o protótipo.

Estrutura fixa:

```
Briefing de handoff · [tarefa] · v1
Objetivo: [o que a etapa deve produzir e para quê]
Contexto: [o que já existe, decisões fechadas que a etapa respeita]
Entrada: [dados e arquivos disponíveis, onde estão]
Saída esperada: [entregável verificável: arquivo existe, base atualizada, painel publica]
Restrições: [o que não pode ser alterado; convenções aplicáveis]
Critério de validação: [como saberemos que rodou certo]
Autonomia: [degrau N0 a N4 quando envolver agente, com guardrails]
Pendências: [o que segue em aberto e quem resolve]
```

---

## Regras transversais (valem para os 12 tipos)

- Toda entrega nasce no formato final de uso do tipo: peça pronta, não estrutura para outra ferramenta terminar. Estrutura sozinha só quando o usuário pedir a estrutura.
- Toda entrega nasce com título e versão; iteração gera v2 com registro do que mudou.
- Entrega substantiva abre com a célula da matriz e a pergunta que responde, e fecha com "o que eu faria a seguir": uma a três ações em ordem de impacto.
- Decisão fechada e hipótese em teste nunca aparecem misturadas sem marcação.
- Pendências fecham a entrega, nomeadas; nenhum bloqueio fica escondido no meio do texto.
- Escolha de pergunta, decisão estrutural de verba, risco reputacional e o que é dito ao cliente saem sempre como recomendação com alternativas, nunca como decisão tomada (R6).
