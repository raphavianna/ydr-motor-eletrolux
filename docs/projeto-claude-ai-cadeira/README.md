# Projeto espelho no Claude.ai: a cadeira em operação diária

Materiais para montar o Projeto no Claude.ai que espelha a cadeira de Direção Executiva de Mídia e Dados. Versão: v2 (a v1 tratava o Projeto como camada de pensamento com produção visual em etapa separada; a v2 o torna autossuficiente, com a peça final como entrega default).

## Divisão de ambientes

O Projeto é autossuficiente: produz a peça final com o potencial completo do ambiente Claude.ai (artifacts em HTML, execução de código, criação de arquivos xlsx, docx e pdf, busca na web quando disponível). A fronteira com o Code é estreita e definida pelo que exige repositório e execução recorrente, não pela complexidade da tarefa.

| Ambiente | Papel |
|---|---|
| Claude Code (repositório da cadeira) | O que exige repositório e recorrência: bases versionadas por cliente e concorrência, ingestão automatizada de fontes, pipelines de dado em produção, agentes de operação via API, engenharia de produto |
| Claude.ai (este Projeto) | Todo o resto, completo e no formato final: apresentações em HTML, planilhas e modelos, dashboards, planos e reports, pautas, textos, fluxos, cronogramas, teses, briefs, análises com código e briefings de handoff para o Code |

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
4. No Projeto, conferir que artifacts, análise com código e criação de arquivos estão habilitados na conta, porque as entregas default dependem deles.
5. Rodar os seis testes abaixo antes de usar em produção.

## Como testar

1. Matriz e padrão: colar um dado simples de campanha e pedir leitura. Esperado: abertura com a célula da matriz (mandato × prática), classificação da pergunta (diagnóstico, previsão ou decisão), insight em cinco partes e fechamento com "o que eu faria a seguir".
2. Anti-alucinação: pedir um benchmark de CPM da categoria sem fornecer dado. Esperado: recusa a estimar por conhecimento geral, marcação [a confirmar] com onde buscar, e o resto da entrega estruturado normalmente.
3. Produção completa de apresentação: pedir uma apresentação de defesa de plano com um dado simples fornecido. Esperado: peça pronta em HTML, com dado em gráfico, sem parar em roteiro nem perguntar se pode produzir a peça visual.
4. Produção completa de planilha: pedir um modelo de cenários de verba com margem fornecida. Esperado: arquivo xlsx com abas de premissas, cálculo e resultado, fórmulas vivas e premissas com fonte.
5. Roteamento estreito: pedir "monta o pipeline de ingestão dos reports da Kantar". Esperado: o desenho do pipeline e o contrato de qualidade produzidos no Projeto, mais o briefing de handoff apenas para a implementação no repositório, sem empurrar a parte pensável para o Code.
6. Doutrina sob pressão: apresentar um ROAS de plataforma alto e pedir mais verba no canal. Esperado: a escada da prova aplicada (atribuição não é incrementalidade), proposta de teste antes de escalar, no padrão do exemplo do dossiê.

## Manutenção

O espelho segue versionamento explícito: mudança na doutrina da cadeira (nova prática, mandato revisado, regra nova, mudança na escada de autonomia) atualiza primeiro os documentos deste diretório, em versão nova, e depois as instruções e os anexos do Projeto no Claude.ai. Decisão específica de cliente, de concorrência ou do motor de insights não entra no espelho.
