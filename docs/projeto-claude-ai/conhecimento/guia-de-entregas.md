# Guia de entregas: operação diária do motor

Documento de conhecimento do Projeto de operação diária no Claude.ai. Versão: v1.

Especificação e template de cada tipo de entrega da função. O template é o formato de referência: os campos fixos permanecem em toda entrega do tipo; a profundidade de cada campo se adapta ao caso. Toda entrega segue o filtro editorial e as regras de dado das instruções do Projeto.

---

## 1. Radar diário

Quando usar: pico ou queda relevante nas últimas 24h, disparado por relevância do tema, nunca por calendário. Sem sinal relevante, não há radar.

Audiência: mídia e performance, PR de resposta rápida, community management.

Template (3 a 5 linhas no total):

```
Radar [marca] · [território] · [data]
Sinal: [o que se moveu e o delta observado]
Fonte: [fonte(s); uma fonte = "observação, aguarda confirmação cruzada"]
Leitura: [lente e o que o movimento indica, em uma frase]
Ação: [ação disponível na janela, ou "monitorar até (condição)"]
```

## 2. Brief semanal

Quando usar: consolidação dos deltas da semana, por marca.

Audiência: planejamento, criação, mídia, atendimento e cliente.

Estrutura fixa:

1. Top 3 a 5 insights da semana. Cada item traz: sinal e delta, fontes que confirmaram, lente, estado no ciclo e ação sugerida.
2. Status dos insights em ação (o que segue em execução, desde quando).
3. Seção de retorno: ações da semana anterior e resultado medido de cada uma. Sem resultado ainda, dizer isso e a data prevista de leitura.
4. Observações: sinais de fonte isolada que aguardam confirmação.

## 3. Relatório mensal

Quando usar: leitura de cultura e jornada do mês, por marca; padrão cross-marca quando fizer sentido.

Duas versões a partir da mesma base:

- Versão interna de conta: liderança da agência, marketing e C-level da marca. Inclui seção de retorno da conta, resultado medido do mês anterior.
- Versão de mercado: sem dado sensível de conta, leitura de indústria e tendência. Antes de produzir, listar o que foi retirado da versão interna e por quê (triagem explícita, não duas apurações).

Estrutura fixa da versão interna:

1. Sumário executivo (meia página).
2. Leitura de cultura do mês.
3. Leitura de jornada do mês.
4. Cruzamento das duas lentes (exclusivo da cadência mensal).
5. Seção de retorno: ações do mês anterior e resultado medido.
6. Recomendações priorizadas por magnitude do delta.
7. Pendências e observações.

## 4. Roteiro de deck e apresentação

Quando usar: qualquer apresentação da função, interna ou de cliente. O roteiro estrutural vem antes de qualquer produção visual; a peça visual é etapa separada, ativada só depois da aprovação da estrutura.

Formato por slide:

```
## Slide N: [título]
Mensagem-chave: [uma frase que sustenta o slide sozinha]
Pontos de apoio: [2 a 4 itens]
Nota do apresentador: [contexto de fala, só quando houver]
```

Regras do tipo: separar decisão fechada de hipótese em teste já no primeiro slide em que as duas convivem; pendências ganham slide próprio perto do fim; declarar teto de slides assumido quando o pedido não fixar um.

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

Estrutura fixa: etapas sequenciais numeradas, cada uma com entregável, responsável, dependência e status. Espelha a disciplina do motor: nenhuma etapa começa antes de a anterior estar rodada e validada; o gate de aprovação entre etapas é explícito.

```
| # | Etapa | Entregável | Responsável | Depende de | Status |
```

Status possíveis: concluída, em andamento, aguardando aprovação, pendente. Datas só quando o usuário fornecer; sem data, ordenar por dependência.

## 7. Fluxo de trabalho

Quando usar: desenhar ou revisar um processo da função ou de uma conta.

Estrutura fixa: estados nomeados (espelhando o padrão do ciclo de cinco estados: substantivo, rastreável), gatilho de entrada de cada estado, responsável e saída. Todo fluxo novo nasce como versão de trabalho v1, com pontos de atenção listados ao fim, no padrão da hierarquia v1 do blueprint.

## 8. Textos e comunicações

Quando usar: e-mails, mensagens, resumos executivos, comunicados, textos de rotina.

Regras do tipo: identificar audiência e objetivo antes de escrever; uma mensagem central por texto; filtro editorial integral; para e-mail, assunto proposto e um só call to action.

## 9. Análise pontual de dados colados

Quando usar: o usuário cola um export, uma tabela ou um relato de dado e pede leitura.

Estrutura fixa:

1. Leitura em prosa: o que o dado mostra, por lente.
2. Aplicação dos três filtros a cada movimento relevante, na ordem: magnitude, confirmação cruzada, ação disponível.
3. Bloco final "estado no ciclo": o que é observação (e qual segunda fonte confirmaria), o que é insight validado, qual ação está disponível.

Regra do tipo: nenhum número que não esteja no dado colado. Comparação com período anterior só quando o dado anterior também estiver disponível; caso contrário, [DADO PENDENTE].

## 10. Briefing de handoff para o Code

Quando usar: o pedido pertence ao ambiente Code (base versionada, ingestão, script, painel, pipeline). Este Projeto entrega a camada de pensamento; a execução vai para o Code, onde a skill agente-de-prompts transforma o briefing em prompt técnico da etapa.

Estrutura fixa:

```
Briefing de handoff · [tarefa] · v1
Objetivo: [o que a etapa deve produzir e para quê]
Contexto: [o que já existe, decisões fechadas que a etapa respeita]
Entrada: [dados e arquivos disponíveis, onde estão]
Saída esperada: [entregável verificável: arquivo existe, base atualizada, painel publica]
Restrições: [o que não pode ser alterado; convenções aplicáveis]
Critério de validação: [como saberemos que rodou certo]
Pendências: [o que segue em aberto e quem resolve]
```

---

## Regras transversais (valem para os 10 tipos)

- Toda entrega nasce com título e versão; iteração gera v2 com registro do que mudou.
- Seção de retorno é obrigatória no brief semanal e no relatório mensal, mesmo vazia ("nenhuma ação fechou ciclo no período").
- Decisão fechada e hipótese em teste nunca aparecem misturadas sem marcação.
- Pendências fecham a entrega, nomeadas; nenhum bloqueio fica escondido no meio do texto.
