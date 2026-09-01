# Padrões de produção das peças

Documento de conhecimento do Projeto de operação diária no Claude.ai. Versão: v1.

Especificação de acabamento das peças finais. O guia de entregas diz o que cada tipo contém; este documento diz como a peça fica pronta em nível best-in-class. Consulte antes de produzir apresentação, planilha, dashboard ou documento.

## 1. Apresentação em HTML

Arco narrativo de defesa, nesta ordem: a pergunta que a apresentação responde; a tese em uma frase; a evidência que a sustenta; a recomendação com tamanho, lugar e prazo; a prova e o custo de estar errado; lacunas e premissas declaradas; próximos passos. Slides de contexto existem para servir a esse arco, não para inventariar tudo o que se sabe.

Tipos de slide e regra de cada um:

- Capa: cliente ou tema, título que carrega a tese (não um rótulo genérico), data e versão.
- Tese: uma frase no centro. Sem bullets.
- Dado: um gráfico dominante por slide, com a leitura escrita na própria página (R1: número sem leitura não sai). Fonte do dado no rodapé do slide.
- Comparação: tabela ou barras lado a lado, com a diferença que importa destacada e dita.
- Recomendação: ação, tamanho, lugar, prazo e dono. Uma recomendação principal por slide.
- Cenários: premissa de cada cenário visível junto do resultado, nunca só o resultado.
- Lacunas e premissas: slide próprio perto do fim, com [a confirmar] nomeados. Lacuna declarada na defesa joga a favor.
- Próximos passos: uma a três ações em ordem de impacto.

Regras visuais:

- Um ponto por slide. Slide que precisa de dois parágrafos é dois slides ou é documento.
- Hierarquia tipográfica clara: título forte, apoio menor, no máximo dois pesos e duas escalas por slide. Fonte de sistema legível em projeção (mínimo equivalente a 20px no corpo).
- Paleta sóbria: fundo neutro, uma cor de destaque usada só para o que decide. Quando o cliente tiver identidade fornecida na conversa, usar; sem identidade fornecida, neutro elegante, nunca cores inventadas "da marca".
- Dado em gráfico, não em parágrafo. Texto corrido em slide só para tese e leitura.
- Sem emoji, sem clipart, sem imagem decorativa que não carrega informação.
- Navegação por setas do teclado e clique, contador de slide discreto, proporção 16:9, legível também em tela pequena.

A peça sai acompanhada do roteiro slide a slide (template no guia de entregas) quando houver contexto de fala relevante.

## 2. Gráficos e visualização de dado

- A pergunta escolhe a forma: comparação entre itens pede barras; evolução no tempo pede linha; participação pede barras empilhadas ou 100% (torta só com poucas fatias e diferença visível); relação entre duas variáveis pede dispersão.
- Barra começa no zero. Linha pode recortar escala, com o recorte declarado.
- Um gráfico responde uma pergunta; a pergunta vira o título do gráfico.
- Destaque na série que importa, resto em neutro. Legenda só quando o rótulo direto não couber.
- Todo gráfico carrega fonte e período do dado. Dado colado pelo usuário é citado como tal.
- Nenhum gráfico decorativo: se a leitura não muda decisão nem entendimento, o gráfico sai.

## 3. Planilha e modelo

Arquitetura fixa de abas:

1. Leia-me: o que o modelo faz, versão, registro do que mudou entre versões, como usar.
2. Premissas: todo input com valor, fonte e marcação [a confirmar] quando faltar dado. Nenhuma constante enterrada em fórmula.
3. Entrada de dados: o que o usuário atualiza, separado do que calcula.
4. Cálculo: fórmulas vivas, encadeadas das premissas. Sem valor digitado por cima de fórmula.
5. Resultado: a leitura final, formatada para decisão (cenários lado a lado, sensibilidade quando couber).

Regras: formatação de moeda e percentual correta; célula de premissa visualmente distinta de célula calculada; validação de dados em campos de escolha; nome de aba e de arquivo sem espaço criativo (padrão: cliente-tema-versao). Modelo que o usuário vai manter ganha instruções de atualização no leia-me.

## 4. Dashboard em HTML

- Hierarquia de decisão: o número que decide no topo, com a leitura escrita ao lado (R1); suporte e detalhe abaixo.
- Todo painel declara período coberto, frescor do dado e fonte, visíveis sem interação.
- Interação a serviço da pergunta: filtro por período, marca ou praça quando a decisão varia por esses cortes; nada de interação ornamental.
- Estado vazio honesto: corte sem dado mostra "sem dado no período", nunca zero que parece medição.
- Funciona em tela cheia para reunião e em tela pequena para consulta.

## 5. Documento executivo

- Título, versão, data, célula da matriz e a pergunta que o documento responde, no topo.
- Sumário executivo de meia página no máximo: as leituras que decidem, não o índice do que vem.
- Prosa em frases completas; tabela para comparação enumerável; bullet para lista de ações.
- Inferência marcada com grau de confiança (R3); métrica-proxy nomeada (R4); pendências ao fim, nomeadas.
- Formato de arquivo: markdown para consumo na conversa; docx ou pdf quando for circular fora dela.

## 6. Acabamento comum a toda peça

- Revisão final antes de entregar: números conferem com a fonte, totais fecham, nenhum placeholder esquecido, nenhuma célula ou slide de rascunho.
- Versão marcada na peça; iteração gera versão nova com registro do que mudou.
- A mensagem que acompanha a peça na conversa traz a célula da matriz, a pergunta respondida, as decisões de produção relevantes e o "o que eu faria a seguir".
