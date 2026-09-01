# Projeto espelho no Claude.ai: operação diária do motor

Materiais para montar o Projeto no Claude.ai que espelha a função deste repositório. Versão: v1.

## Divisão de ambientes

| Ambiente | Papel |
|---|---|
| Claude Code (este repositório) | Trabalho complexo e recorrente: base versionada, ingestão de reports, scripts, modelagem e publicação do painel |
| Claude.ai (Projeto espelho) | Operação diária da função: apresentações, pautas de reunião, textos, fluxos, cronogramas, radares, briefs, estruturas de relatório, análises pontuais e briefings de handoff para o Code |

Os dois compartilham a mesma essência: o motor de insights culturais e comportamentais, seu ciclo de cinco estados, as duas lentes, o critério de três filtros e as cadências de output. O espelho carrega a arquitetura da função (etapas 1 e 2), sem as atualizações específicas do piloto Eletrolux (briefing técnico, schema de dados, roadmap e features ancoradas), que seguem evoluindo só neste repositório.

## Arquivos

| Arquivo | Destino no Claude.ai |
|---|---|
| `instrucoes-do-projeto.md` | Colar integralmente no campo de instruções do Projeto |
| `conhecimento/blueprint-motor-insights-consolidado.md` | Anexar ao conhecimento do Projeto |
| `conhecimento/guia-de-entregas.md` | Anexar ao conhecimento do Projeto |

## Montagem, passo a passo

1. No Claude.ai, criar um Projeto. Nome sugerido: "Motor de insights · operação diária".
2. Colar o conteúdo de `instrucoes-do-projeto.md` no campo de instruções, sem edição.
3. Anexar os dois arquivos de `conhecimento/` ao conhecimento do Projeto, com os nomes de arquivo preservados (as instruções os referenciam pelo nome).
4. Rodar os três testes abaixo antes de usar em produção.

## Como testar

1. Roteamento: pedir "cria a base versionada de termos da marca X". Esperado: o Projeto aponta em uma linha que a execução pertence ao Code e oferece o briefing de handoff, sem simular a tarefa.
2. Anti-simulação: pedir um radar diário sem colar dado nenhum. Esperado: estrutura completa com marcações [DADO PENDENTE], nenhum número inventado.
3. Entrega padrão: pedir uma pauta de reunião sobre um tema qualquer. Esperado: estrutura do guia de entregas, com decisão esperada por bloco, versão v1 e filtro editorial aplicado.

## Manutenção

O espelho segue a mesma disciplina de versionamento do motor: mudança na arquitetura da função (novo pilar de fonte, mudança de cadência, hierarquia revisada) atualiza primeiro os documentos deste diretório, em versão nova, e depois os anexos do Projeto no Claude.ai. Decisão específica do piloto Eletrolux não entra no espelho.
