# Projeto espelho no Claude.ai: a cadeira em operação diária

Materiais para montar o Projeto no Claude.ai que espelha a cadeira de Direção Executiva de Mídia e Dados. Versão: v1.

## Divisão de ambientes

| Ambiente | Papel |
|---|---|
| Claude Code (repositório da cadeira) | Trabalho complexo e recorrente: bases versionadas por cliente e concorrência, ingestão de fontes, scripts, modelagem, painéis, pipelines e agentes de operação |
| Claude.ai (este Projeto) | Operação diária da função: apresentações e roteiros de deck, pautas de reunião, textos, fluxos, cronogramas, estruturas de plano e report, teses, briefs, análises pontuais e briefings de handoff para o Code |

Os dois compartilham a mesma essência: a identidade da cadeira, a tese (Ehrenberg-Bass, o que mídia faz e não faz, o consumidor aumentado, postura mind-centric), a matriz de mandatos e práticas, a doutrina de decisão, o padrão de insight e as regras inegociáveis. O espelho carrega a doutrina da cadeira e nada do que é específico de cliente ou de projeto: o motor de insights do piloto Eletrolux, briefings técnicos, schemas de dado e roadmaps seguem evoluindo apenas no repositório.

## Arquivos

| Arquivo | Destino no Claude.ai |
|---|---|
| `instrucoes-do-projeto.md` | Colar integralmente no campo de instruções do Projeto |
| `conhecimento/cadeira-dossie.md` | Anexar ao conhecimento do Projeto |
| `conhecimento/guia-de-entregas.md` | Anexar ao conhecimento do Projeto |

## Montagem, passo a passo

1. No Claude.ai, criar um Projeto. Nome sugerido: "Direção de Mídia e Dados · operação diária".
2. Colar o conteúdo de `instrucoes-do-projeto.md` no campo de instruções, sem edição.
3. Anexar os dois arquivos de `conhecimento/` ao conhecimento do Projeto, com os nomes de arquivo preservados (as instruções os referenciam pelo nome).
4. Rodar os quatro testes abaixo antes de usar em produção.

## Como testar

1. Matriz e padrão: colar um dado simples de campanha e pedir leitura. Esperado: abertura com a célula da matriz (mandato × prática), classificação da pergunta (diagnóstico, previsão ou decisão), insight em cinco partes e fechamento com "o que eu faria a seguir".
2. Anti-alucinação: pedir um benchmark de CPM da categoria sem fornecer dado. Esperado: recusa a estimar por conhecimento geral, marcação [a confirmar] com onde buscar, e o resto da entrega estruturado normalmente.
3. Roteamento: pedir "monta o pipeline de ingestão dos reports da Kantar". Esperado: uma linha dizendo que a execução pertence ao Code e o briefing de handoff no template do guia, sem simular a tarefa.
4. Doutrina sob pressão: apresentar um ROAS de plataforma alto e pedir mais verba no canal. Esperado: a escada da prova aplicada (atribuição não é incrementalidade), proposta de teste antes de escalar, no padrão do exemplo do dossiê.

## Manutenção

O espelho segue versionamento explícito: mudança na doutrina da cadeira (nova prática, mandato revisado, regra nova, mudança na escada de autonomia) atualiza primeiro os documentos deste diretório, em versão nova, e depois as instruções e os anexos do Projeto no Claude.ai. Decisão específica de cliente, de concorrência ou do motor de insights não entra no espelho.
