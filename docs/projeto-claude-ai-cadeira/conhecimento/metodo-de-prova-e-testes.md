# Método de prova e testes

Documento de conhecimento do Projeto de operação diária no Claude.ai. Versão: v1.

Profundidade de método para M3 (prova e reporting) e para toda decisão de verba. Consulte quando a entrega tocar medição, teste, incrementalidade, leitura de report de plataforma ou alocação. As regras aqui detalham D3, D4 e D6 do dossiê e a prática P1; em contradição de princípio, o dossiê e as instruções prevalecem.

## 1. A escada da prova

Quatro degraus, do mais fraco ao mais forte. Toda afirmação de valor declara em qual degrau está.

1. Correlação: duas séries se movem juntas. Sustenta hipótese, não sustenta decisão. Uso legítimo: gerar a pergunta do teste.
2. Atribuição: a plataforma ou o modelo de toque credita conversões a exposições. Auto-relatada, enviesada a favor de quem reporta, cega ao que aconteceria sem o canal. Uso legítimo: operação diária, comparação relativa dentro do mesmo canal, detecção de tendência.
3. Teste incremental: grupo exposto contra grupo controle (holdout geográfico, brand lift, teste de audiência, incrementalidade de retail media). É o degrau que responde "quanto não aconteceria sem". Forte em causalidade, estreito em escopo e janela.
4. Modelagem (MMM): econometria sobre séries agregadas. Única lente que compara todos os canais numa moeda só e enxerga offline, preço, distribuição e sazonalidade. Sensível à especificação; precisa ser calibrada por experimentos.

Regra de uso: subir a escada sempre que o dado permitir; nunca apresentar degrau 2 como se fosse 3 ou 4. Quando a entrega só tem degrau 1 ou 2, dizer isso e propor o desenho que subiria.

## 2. Triangulação

Nenhuma lente decide sozinha. O experimento calibra o MMM e corrige viés; o MMM aloca entre canais; a atribuição opera o dia a dia. Quando as três divergem, a hierarquia para decisão de verba é experimento, depois MMM, depois atribuição.

A divergência é informação, não defeito. O padrão mais comum: atribuição bem acima do incremental medido indica canal que captura demanda criada em outro lugar (típico em busca de marca e em remarketing). A pergunta seguinte é onde essa demanda foi criada e se o investimento deveria migrar para lá.

## 3. Desenho de teste

Todo teste declara, antes de começar, sete componentes. Teste sem critério de decisão declarado antes vira interpretação conveniente depois.

1. Hipótese: o que acreditamos e qual mecanismo explicaria.
2. Unidade de teste: praça, audiência, loja, período. Pareada com o controle no que importa.
3. Controle: o que representa "sem a ação". Holdout limpo vence lookalike de conveniência.
4. Janela: tempo suficiente para o efeito aparecer no elo testado. Efeito de marca não cabe em janela de uma semana.
5. Métrica primária: uma, ligada ao elo da cadeia causal que o teste mira. Secundárias são diagnóstico, não veredito.
6. Critério de decisão: qual resultado sustenta qual ação, declarado antes da leitura (por exemplo: incremental acima de X% do atribuído sustenta o aumento; abaixo, a verba migra).
7. Custos: o custo do teste (verba suspensa, alcance perdido) e o custo de estar errado sem o teste. Quando o segundo supera o primeiro, o teste se paga.

Tipos de teste do repertório da cadeira:

- Holdout geográfico: suspender ou variar investimento em praças pareadas. Serve para incrementalidade de canal e calibragem de MMM. Escolher praças de participação pequena na receita para limitar o custo.
- Brand lift: exposto contra controle em métrica de marca (lembrança, consideração). Em plataforma ou com fornecedor independente; o independente vale mais como prova.
- Incrementalidade em retail media: usar o dado de venda do varejista para comparar comprador exposto e não exposto. É onde a prova causal é mais barata de obter.
- Teste criativo e de mensagem: variação de peça com audiência e verba controladas. Leitura por conteúdo, no contexto certo de comparação.
- Teste de expansão de audiência: fatia de verba para audiência nova com leitura em janela declarada, antes de escalar (D4).

## 4. Leitura por horizonte

Efeitos de ativação aparecem em dias; efeitos de marca se acumulam por meses e extrapolam qualquer janela de atribuição digital. Consequências operacionais:

- Comparação entre canal de ativação e canal de marca dentro de janela curta é estruturalmente enviesada contra marca. Declarar o viés sempre que a comparação aparecer.
- ROI de curto prazo subestima o total quando há efeito de arrasto; a meia-vida do investimento é dado do MMM, não intuição.
- Corte de investimento de marca não cobra o preço no mês do corte. A leitura honesta projeta o custo no horizonte em que ele aparece.

## 5. Checklist de leitura crítica de report de plataforma

Antes de aceitar qualquer número de plataforma em entrega, verificar:

1. Janela de atribuição usada e se mudou no período comparado.
2. Peso de view-through no total creditado.
3. Sobreposição de crédito entre plataformas (a soma dos ROAS reportados costuma superar a receita real).
4. Participação de marca registrada e remarketing no resultado (demanda capturada, não criada).
5. Mudança de metodologia, de pixel ou de modelagem de conversão no período.
6. Se o número é médio ou marginal, e qual dos dois a decisão em pauta exige (D6).

Report que não passa no checklist entra na entrega com a ressalva nomeada, nunca silenciada.

## 6. Quando não há dado

Sem instrumento contratado ou sem série disponível, o padrão da cadeira é: não estimar, estruturar. Nomear a lacuna com [a confirmar], desenhar o baseline manual ou o teste que geraria o dado, e decidir o intervalo até lá pelo princípio da tese (seção 2 do dossiê). Baseline manual que estabiliza é candidato a rotina em P10 e a produto em M4.
