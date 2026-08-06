# Roteiro estrutural do deck mestre: motor de insights culturais e comportamentais (v2)

Etapa 2. Versão 2. Base: blueprint-motor-insights-etapa1-v2.md, mais as decisões de arquitetura fechadas nesta rodada de conversa, ainda fora do blueprint da etapa 1. A versão 1 deste roteiro fica como histórico.

**Registro de mudanças desta rodada:**
- Novo sexto pilar de dado, social intelligence: captura creators em tendência e o conteúdo que produzem, via CreatorIQ, Influencity e TikTok Creative Center, cobrindo três segmentos, creators mainstream, líderes de comunidade e território, e creators de conversão/UGC.
- Webscraping deixa de rodar só via Perplexity e passa a rodar em múltiplos motores de IA: Perplexity, ChatGPT, Gemini e outros a confirmar.
- Reordenação da lista de fontes: webscraping passa a aparecer antes de social listening, não depois.
- Quatro slides novos ou revisados em função dessas três mudanças, um deles como quarto slide de aprofundamento.

**Nota sobre variáveis não preenchidas.** O prompt original de etapa 2 trazia três variáveis sem valor definido nesta rodada: público de referência e teto de slides. Mantenho a mesma suposição da v1: público genérico, calibrado ao registro formal de relatório executivo interno já fixado no filtro editorial, e teto de 18 slides. Este roteiro usa 17.

---

## Slide 1: abertura, propósito do motor e propósito deste documento

**Mensagem-chave:** o motor de insights consolida seis fontes de dado em um ciclo permanente de captura, insight, ação e retorno, e este documento registra tanto a arquitetura fechada na etapa 1 quanto as atualizações de arquitetura desta rodada.

**Pontos de apoio:**
- Motor cíclico, não linear. Cada ação gera um dado de retorno que realimenta a próxima captura.
- Quatro marcas-clientes, cada uma em seu território: iFood, Eletrolux, RD e MRV.
- Já fechado desde a etapa 1: ciclo de cinco estados, duas lentes de leitura, cinco fontes de dado originais, critério de três filtros, três cadências de output.
- Novidades desta rodada, ainda fora do blueprint da etapa 1: estrutura de duas versões do relatório mensal, hierarquia de escopo, leitura e ação em versão de trabalho v1, sexto pilar de dado (social intelligence) e ampliação do webscraping para múltiplos motores de IA.

**Nota do apresentador:** separar, já no primeiro slide, o que é decisão fechada do que é hipótese em teste. Essa distinção evita que a hierarquia v1 e o sexto pilar, ambos apresentados mais adiante, sejam lidos como estrutura definitiva.

## Slide 2: o ciclo do motor, cinco estados de um insight

**Mensagem-chave:** nenhum insight nasce pronto. Ele passa por cinco estados rastreados, do sinal bruto ao resultado medido, e é o resultado medido que reabre o ciclo.

**Pontos de apoio:**
- Sinal bruto, insight validado, ação recomendada, ação tomada, resultado medido.
- A base de termos e insights é versionada. Cada termo carrega histórico de volumetria por período, cada insight carrega histórico de estado.
- O resultado medido de uma ação vira o sinal de entrada da próxima captura.

**Nota do apresentador:** o estado "resultado medido" sustenta a seção de retorno dos outputs semanal e mensal, retomada no slide 6.

## Slide 3: duas lentes de leitura, sempre separadas

**Mensagem-chave:** cultura e jornada de consumo são lidas de forma independente, e só se cruzam com profundidade na leitura mensal.

**Pontos de apoio:**
- Cultura e tendências: o que se move no território, independente de intenção de compra.
- Jornada de comportamento e consumo: posição no funil, pré-consideração, consideração, decisão, pós-compra, e o motivo por trás da escolha.
- O cruzamento das duas lentes fica reservado à cadência mensal. O radar diário e o brief semanal tratam cada lente à parte.

## Slide 4: as seis fontes de dado e o papel de cada uma

**Mensagem-chave:** cada fonte cobre uma função específica do motor; nesta rodada o conjunto ganha um sexto pilar e o webscraping passa por ampliação e reposicionamento na lista.

**Pontos de apoio:**
- Semrush + Gemini: base de termos, palavras-chave, território e etapa de funil, com volumetria e delta entre períodos. Sem integração via API nesta fase; estimativa, volumetria e quality score seguem manuais, entre Claude e Semrush.
- Google Trends: picos e quedas diários ou semanais por território, sobre a mesma base de palavras-chave.
- Webscraping via múltiplos motores de IA (atualizado e reposicionado nesta rodada): coleta de publicações sobre marca, concorrente e território, rodando em paralelo em mais de um motor, Perplexity, ChatGPT, Gemini e outros a confirmar, e não mais só Perplexity. Passa a aparecer antes de social listening na ordem da lista, por reunir a coleta bruta de publicação que alimenta a leitura que vem a seguir.
- Social listening: menções de marca, território e concorrente, tom positivo e negativo, via Brandwatch e uma segunda ferramenta ainda a confirmar (pendência aberta, slide 15), complementada por observação direta em Meta, TikTok e X. Cobre menção à marca; não cobre o creator como unidade, ponto que passa a ser coberto pelo sexto pilar.
- Meta Ads Library: benchmark de criativo por objetivo, indústria e território, incluindo tendência internacional como antecipação de tendência local.
- Social intelligence (novo nesta rodada): captura creators de conteúdo em tendência e o conteúdo que produzem, via CreatorIQ, Influencity e TikTok Creative Center. Detalhado no slide 8.

**Nota do apresentador:** o mapeamento formal de cada fonte, incluindo as duas atualizadas nesta rodada, contra a hierarquia de escopo e leitura ainda não existe. Esse gap é frente de aprofundamento no slide 12 e decisão de etapa 3.

## Slide 5: critério de três filtros, quando um sinal vira insight

**Mensagem-chave:** um sinal só sobe a insight compartilhável depois de passar, nesta ordem, por magnitude, confirmação cruzada e ação disponível.

**Pontos de apoio:**
- Magnitude do delta: desvio relevante frente ao período anterior, não ruído normal.
- Confirmação cruzada: duas ou mais fontes na mesma direção. Fonte isolada fica como observação, não como insight.
- Ação disponível: existe pelo menos uma ação possível associada ao sinal.

**Nota do apresentador:** o critério está definido em termos qualitativos. A tradução de magnitude relevante e confirmação cruzada em regra prática, por fonte e por marca, ainda não existe; é a frente de aprofundamento do slide 11.

## Slide 6: cadência de output, diário, semanal e mensal

**Mensagem-chave:** as três cadências têm audiência e formato próprios, e as duas de maior escopo, semanal e mensal, sempre carregam retorno de ação, nunca só insight novo.

**Pontos de apoio:**
- Diário: radar curto, três a cinco linhas, disparado por relevância do tema, não por calendário fixo. Audiência: mídia e performance, PR de resposta rápida, community management.
- Semanal: brief estruturado, top três a cinco insights, ação sugerida por item e seção de retorno das ações da semana anterior. Audiência: planejamento, criação, mídia, atendimento e cliente.
- Mensal: relatório executivo, leitura de cultura e jornada, padrão cross-marca quando fizer sentido, resultado medido do mês anterior. Audiência: liderança da agência, marketing e C-level da marca.

## Slide 7: atualização desta rodada, duas versões do output mensal

**Mensagem-chave:** o relatório mensal passa a ter duas versões a partir da mesma base de insight, uma interna de conta e uma de mercado; a decisão é nova desta rodada e ainda não está no blueprint da etapa 1.

**Pontos de apoio:**
- Versão interna: liderança da agência, marketing e C-level da marca, com seção de retorno específica da conta.
- Versão de mercado: sem dado sensível de conta, foco em leitura de indústria e tendência, usada como captura de lead ou material de apresentação a outros clientes.
- Pendência explícita para a etapa 3: qual dado pode sair da conta do cliente e virar conteúdo de mercado ainda não tem resposta.

**Nota do apresentador:** essa pendência é decisão de governança de dado, não detalhe editorial. Ela define o que a versão de mercado pode ou não conter, antes de qualquer produção de conteúdo.

## Slide 8: atualização desta rodada, sexto pilar, social intelligence

**Mensagem-chave:** o motor passa a rastrear não só o que se fala sobre a marca, mas quem produz o conteúdo em tendência; a decisão é nova desta rodada e ainda não está no blueprint da etapa 1.

**Pontos de apoio:**
- Três segmentos de creator cobertos: creators mainstream, alcance amplo e tendência de território ou nacional; líderes de comunidade e território, alcance local ou de nicho, autoridade dentro de um grupo específico; creators de conversão/UGC, conteúdo orientado a performance, formato depoimento ou uso de produto.
- Ferramentas previstas: CreatorIQ, descoberta e gestão de creator em escala, com dado de performance de campanha; Influencity, base de creator com análise de audiência por localização, interesse e qualidade de engajamento; TikTok Creative Center, descoberta de creator e conteúdo em tendência por território dentro do TikTok, com conexão a creators via Creator Marketplace.
- Mapeamento inicial ferramenta-segmento, hipótese a validar na etapa 3: TikTok Creative Center e CreatorIQ para creators mainstream; Influencity e CreatorIQ para líderes de comunidade e território; CreatorIQ e TikTok Creative Center para creators de conversão e UGC.

**Nota do apresentador:** a diferença frente a social listening é o objeto de captura. Listening rastreia menção à marca, território e concorrente; social intelligence rastreia o creator como unidade, o que ele produz e sua tendência de alcance, independente de o conteúdo citar a marca. Duas perguntas seguem sem resposta e são tratadas no slide 14: qual critério define cada segmento de creator, e se este pilar alimenta o funil de sinal do critério de três filtros ou funciona como camada de ativação de ação, depois que o insight já existe.

## Slide 9: hierarquia de escopo, leitura e ação, versão de trabalho v1

**Mensagem-chave:** a hierarquia organiza o motor em quatro eixos, escopo, leitura, ação e fechamento de ciclo; é apresentada aqui como versão de trabalho, sujeita a revisão conforme a etapa 3 avança.

**Pontos de apoio:**
- Eixo de escopo, do mais amplo ao mais específico: marcas e concorrentes, território, consumidor.
- Eixo de leitura, aplicado sobre esse escopo: cultura e tendências, jornada de comportamento e consumo.
- Ponto de virada: insight, o mesmo estado "insight validado" do ciclo de cinco estados.
- Eixo de ação, lista aberta: comunicação, conteúdo, interação, produto, mídia, stunt PR, entre outras. Interação reúne marca, engajamento, lead e venda como tipos de resultado, não como um terceiro estágio fixo.
- Fechamento do ciclo: o resultado medido realimenta o topo, marca, território e consumidor, reabrindo a captura.

**Nota do apresentador:** esta é a v1 da hierarquia. Os pontos de atenção do slide seguinte já identificam onde ela ainda não resolve todos os casos, incluindo os dois acréscimos desta rodada.

## Slide 10: pontos de atenção da hierarquia v1

**Mensagem-chave:** a versão atual da hierarquia deixa cinco questões estruturais em aberto; nenhuma delas invalida seu uso como ponto de partida.

**Pontos de apoio:**
- A posição de tendência dentro do eixo de escopo pode subordinar a leitura de cultura ao consumidor, quando cultura deveria ser lida de forma independente de intenção de compra.
- A jornada de funil, de pré-consideração a pós-compra, ainda não tem posição explícita própria dentro da hierarquia.
- As fontes de dado ainda não têm mapeamento formal contra cada camada da hierarquia.
- Concorrentes no mesmo nível de marcas dobra a superfície de observação por território, consumidor e tendência, e o volume de concorrentes por marca ainda não está definido.
- O sexto pilar, social intelligence, e a ampliação do webscraping para múltiplos motores são atualizações desta rodada, posteriores ao desenho do eixo de escopo e leitura, e ainda não entraram nesta versão da hierarquia.

**Nota do apresentador:** apresentar as cinco questões como agenda de refinamento da etapa 3, não como falha de estrutura. A hierarquia v1 cumpre a função de organizar o raciocínio agora; não precisa estar fechada para orientar a etapa 3.

## Slide 11: aprofundamento, operacionalizar o critério de três filtros

**Mensagem-chave:** transformar magnitude relevante e confirmação cruzada em regra prática, por fonte e por marca, decide se o critério de três filtros funciona na operação ou fica só no papel.

**Pontos de apoio:**
- Magnitude: sem limiar numérico definido; dado real de volumetria por fonte ainda não existe, depende da etapa 4.
- Confirmação cruzada: sem regra explícita sobre qual combinação de fontes conta, duas fontes quaisquer ou pares específicos como Trends e social listening.
- Ação disponível: sem catálogo de referência por tipo de sinal. A lista continua aberta, mas um catálogo reduz o tempo de decisão por marca.

**Nota do apresentador:** entre as frentes possíveis, estas quatro foram escolhidas por gerarem mais ambiguidade operacional ou impacto direto na etapa 3, definição e aprovação de fontes, fluxos e métricas. Uma quarta frente foi somada nesta rodada, o próprio pilar de social intelligence (slide 14), por ser a decisão mais nova e com menos regra fechada até aqui.

## Slide 12: aprofundamento, mapear as fontes contra a hierarquia

**Mensagem-chave:** cada fonte de dado precisa de um lugar declarado na hierarquia de escopo e leitura; hoje esse mapeamento não existe, e as duas atualizações desta rodada tornam a lacuna maior.

**Pontos de apoio:**
- Semrush + Gemini e Google Trends alimentam sobretudo o eixo de leitura de jornada, por partirem de intenção de busca.
- Webscraping via múltiplos motores de IA e social listening cobrem cultura e jornada ao mesmo tempo, dependendo do termo monitorado, e essa dupla cobertura ainda não está formalizada.
- Meta Ads Library serve o eixo de ação, como referência de criativo, mais do que o eixo de leitura.
- Social intelligence provavelmente serve ao eixo de leitura de cultura, por captar o que ganha tração de conteúdo independente de intenção de compra, mas também toca o eixo de ação, ao apontar creator disponível para uma campanha depois de um insight validado; a camada exata ainda não está definida, aprofundada no slide 14.
- Nenhuma fonte está mapeada explicitamente contra o eixo de escopo, marca, concorrente, território, consumidor.

**Nota do apresentador:** sem esse mapeamento, o risco é a leitura de cultura, que deveria ser independente de intenção de compra, acabar dominada por fontes ancoradas em busca, repetindo o viés já registrado no slide 10.

## Slide 13: aprofundamento, a arquitetura de duas versões do mensal

**Mensagem-chave:** separar a versão interna da versão de mercado do relatório mensal é decisão editorial e de governança de dado ao mesmo tempo, e a etapa 3 precisa resolver as duas juntas.

**Pontos de apoio:**
- Editorial: a versão de mercado exige um nível de generalização que a versão interna não tem, sob risco de repetir dado de conta em formato de captura de lead.
- Governança de dado: falta a regra que define o que é dado de conta, e não sai, e o que é padrão de indústria, e pode sair.
- Operacional: as duas versões partem da mesma base de insight, o que exige um processo de triagem antes de cada publicação, não duas apurações separadas.

**Nota do apresentador:** nenhuma decisão sobre essa regra deve ser tomada nesta estrutura. Ela fica registrada como pendência explícita para a etapa 3.

## Slide 14: aprofundamento, operacionalizar o pilar de social intelligence

**Mensagem-chave:** social intelligence só funciona como pilar de dado se tiver critério de segmentação, fonte de coleta definida por segmento e resposta para uma pergunta estrutural, o pilar alimenta sinal ou alimenta ação.

**Pontos de apoio:**
- Critério de segmentação: sem definição objetiva do que separa creator mainstream, líder de comunidade e território, e creator de conversão e UGC, seja faixa de alcance, taxa de engajamento ou tipo de conteúdo. Sem esse critério, a classificação fica subjetiva por marca.
- Status de integração: não definido se CreatorIQ, Influencity e TikTok Creative Center entram via API ou seguem o modelo manual já usado para Semrush nesta fase; decisão de etapa 3.
- Sinal ou ação: o pilar pode alimentar o funil de três filtros como qualquer outra fonte, creator em tendência como sinal de cultura, ou pode funcionar como camada de ativação, para a equipe indicar creator disponível depois que um insight já foi validado. As duas funções não são excludentes, mas mudam o desenho do fluxo de dado e merecem decisão explícita antes da etapa 3.
- Sobreposição com social listening: menção de creator sobre a marca pode aparecer nas duas fontes ao mesmo tempo; falta regra sobre qual fonte é dona desse dado para efeito de confirmação cruzada.

**Nota do apresentador:** nenhuma decisão sobre estes quatro pontos deve ser tomada nesta estrutura. Eles entram como pauta de etapa 3, junto com o setup técnico de conectores já previsto para essa etapa.

## Slide 15: pontos em aberto do projeto

**Mensagem-chave:** seis pendências seguem sem resposta, quatro desde a etapa 1 e duas somadas nesta rodada, e nenhuma delas bloqueia a aprovação desta estrutura de conteúdo.

**Pontos de apoio:**
- Nome exato da segunda ferramenta de social listening, além do Brandwatch.
- Qual dado pode sair da conta do cliente e virar conteúdo da versão de mercado do relatório mensal.
- Definição de filtros e territórios exatos por marca, nacional, estado ou capital.
- Se a etapa 4 mira retenção e expansão de conta existente, ou pitch de novo negócio.
- Critério de segmentação dos três tipos de creator do pilar social intelligence (novo, nesta rodada).
- Status de integração, via API ou manual, das ferramentas CreatorIQ, Influencity e TikTok Creative Center (novo, nesta rodada).

**Nota do apresentador:** as seis entram formalmente na pauta da etapa 3; a pendência sobre o foco da etapa 4 entra também na etapa 4, por definir o próprio objetivo do business case.

## Slide 16: status do fluxo de cinco etapas

**Mensagem-chave:** o projeto avança por aprovação sequencial. A etapa 1 está concluída, e as etapas 2 a 4 seguem aguardando aprovação antes de qualquer execução.

**Pontos de apoio:**
- Etapa 1, captura e estruturação do pedido em prompt: concluída.
- Etapa 2, estrutura e fluxo de trabalho para a migração ao Claude Code: em aprovação; esta estrutura de conteúdo, já na sua v2, faz parte dela.
- Etapa 3, fontes, fluxos e métricas, incluindo setup técnico de conectores: aguardando aprovação. Reúne a maior parte das pendências abertas nesta rodada.
- Etapa 4, business case com dados reais e checkpoint de validação com a marca: aguardando aprovação.
- Etapa 5, escala: contínua. Cada nova frente aprovada reaciona a mesma disciplina de prompt, via a skill agente-de-prompts.

## Slide 17: encaminhamento, da estrutura de conteúdo à peça visual

**Mensagem-chave:** este documento encerra a etapa de conteúdo, já incorporando as três mudanças de arquitetura desta rodada. A produção visual é uma etapa separada, ativada só depois da aprovação desta estrutura.

**Pontos de apoio:**
- Formato final ainda não decidido: HTML animado via skill frontend-slides, ou apresentação via skill pptx.
- A escolha de formato depende da audiência final do deck, que ainda não está definida nesta etapa.
- Nenhuma peça visual, dashboard ou dado real deve ser produzido antes dessa aprovação.

**Nota do apresentador:** ao aprovar esta estrutura, o próximo passo é definir a audiência final e então acionar a skill de produção visual correspondente.
