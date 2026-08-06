# ydr-motor-eletrolux

Motor de insights culturais e comportamentais — **piloto Eletrolux LatAm**.

Repositório de trabalho da migração ao Claude Code do motor de inteligência cultural e comportamental, testado aqui com um cliente (Eletrolux) e quatro territórios (Brasil, México, Argentina, Colômbia) antes de generalizar para o restante do portfólio.

O documento-mãe que rege este repositório é [`docs/briefing-tecnico-piloto-eletrolux.md`](docs/briefing-tecnico-piloto-eletrolux.md). Ele é a fonte de verdade; qualquer decisão técnica é validada contra ele antes de rodar.

## O que o motor faz

Ciclo permanente de cinco estados, nunca linear:

```
Sinal bruto → Insight validado → Ação recomendada → Ação tomada → Resultado medido ↻
```

O resultado medido volta como novo sinal bruto e reabre a captura. A base de termos e insights é **versionada, nunca sobrescrita** (briefing §2.1, §5.3).

## Estrutura do repositório

Convenção fixada no briefing §5.1:

| Caminho | Conteúdo |
|---|---|
| `data/raw/{fonte}/{territorio}/{ano-mes}/` | Reports originais, sem tratamento |
| `data/master/` | Base mestre versionada (JSON Lines por lote + view `latest` gerada por script) |
| `app/` | Painel (publicação estática, sem backend vivo) |
| `docs/` | Documentação; `docs/referencias/` guarda os documentos das etapas 1 e 2 |

Enumerações fixas do piloto:

- **Fontes** (`{fonte}`): `semrush`, `similarweb`, `trends`
- **Territórios** (`{territorio}`): `BR`, `MX`, `AR`, `CO`

Os diretórios de `data/raw/` já trazem o esqueleto fonte × território; as pastas `{ano-mes}` são criadas na ingestão (etapa 3+). Arquivos `.gitkeep` seguram os diretórios ainda vazios.

## Convenções que não mudam

- **Sem dado simulado.** Se um conector (Semrush, Similarweb) não estiver disponível numa etapa, a etapa **para e reporta**, nunca inventa dado (briefing §5.4).
- **Credenciais nunca no repositório.** Chaves de API são geridas pelo conector MCP do ambiente Code (§5.4).
- **Histórico bruto imutável.** Um arquivo JSON Lines por lote de ingestão, nunca editado depois de criado. A view `latest` é derivada e pode ser recriada a qualquer momento (§5.3).
- **Idioma local por território**, sem tradução ou normalização automática entre territórios nesta fase (§5.5): pt-BR, es-MX, es-AR, es-CO.
- **Painel lê só base versionada.** Nenhuma chamada de API em tempo de execução no painel publicado — compatível com publicação estática no Netlify (§3.3).
- **Interface atemporal.** Sem marcação de "novo" em qualquer elemento do painel (§5.7).

## Taxonomia de etapa de funil (briefing §5.6)

| Etapa | Intenção |
|---|---|
| `descoberta` | O que é, para que serve |
| `conversao` | Comprar, preço, onde comprar |
| `atendimento` | Cancelar, reclamação, suporte |

## Fluxo de migração — dez etapas

Cada etapa recebe seu próprio prompt técnico (via skill `agente-de-prompts`) e só começa depois de a anterior estar rodada e validada.

| # | Etapa | Status |
|---|---|---|
| 1 | Setup do projeto e repositório | Em andamento (este commit) |
| 2 | Estruturação da base mestre v1 | Pendente |
| 3 | Ingestão de reports Similarweb e Semrush (quebra mensal) | Pendente |
| 4 | Revisão do modelo da base | Pendente |
| 5 | Expansão de termos, palavras-chave e demais dados | Pendente |
| 6 | Definição das abas do painel ("search intel") | Pendente |
| 7 | Primeira modelagem do painel piloto | Pendente |
| 8 | Ajustes | Pendente |
| 9 | Refino de UX via Claude Design | Pendente |
| 10 | Publicação, Netlify | Pendente |

## Documentação de referência

- [`docs/briefing-tecnico-piloto-eletrolux.md`](docs/briefing-tecnico-piloto-eletrolux.md) — documento-mãe do piloto
- [`docs/referencias/blueprint-motor-insights-etapa1-v2.md`](docs/referencias/blueprint-motor-insights-etapa1-v2.md) — blueprint da etapa 1 (v2)
- [`docs/referencias/roteiro-deck-motor-insights-etapa2-v2.md`](docs/referencias/roteiro-deck-motor-insights-etapa2-v2.md) — roteiro estrutural do deck da etapa 2 (v2)
- [`docs/referencias/apresentacao-motor-insights-etapa2.html`](docs/referencias/apresentacao-motor-insights-etapa2.html) — apresentação executiva da etapa 2

## Pendências conhecidas (não bloqueiam a etapa 1)

- Nome exato da segunda ferramenta de social listening, além do Brandwatch.
- Status de integração (API ou manual) de CreatorIQ, Influencity e TikTok Creative Center.
- Critério de segmentação dos três tipos de creator do pilar social intelligence.
- Concorrentes por território para o piloto (a identificar na etapa 2, metodologia em §3.4).
