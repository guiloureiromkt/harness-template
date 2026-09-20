# <NOME DO HARNESS> · arquivo mãe

> Preencha os campos entre `< >`. Apague esta linha quando terminar. Se tiver a skill `mentoria:harness`, ela preenche por você a partir da ficha.

## Quem lê este arquivo (leia primeiro)

Este repositório tem dois tipos de sessão, e as regras são diferentes para cada um:

- **Sessão de construção:** alguém no teclado mudando o que este harness é (código, skills, regras). Segue o ciclo (`intent → spec → plan → build → test`) e o bloco do cycle abaixo, se existir.
- **Rotina:** um loop rodando sozinho (cron, GitHub Actions), escrevendo as próprias saídas em `saida/` ou pedindo aprovação em `aprovar/`. **Rotina é o produto funcionando, não uma edição: não precisa de plano.** Ela continua sem poder fazer push em `main`, apagar coisa ou executar ação para fora sem arquivo em `aprovado/`.

## Propósito
<Uma frase: o que este harness faz, para quem, e o que ele nunca faz. Ex.: "Opera a mídia paga da Garimp.ai: lê, propõe e, com aprovação, executa. Não produz criativo, não mexe em conteúdo orgânico.">

## Marca
<Qual pasta de marca este harness lê antes de produzir, e onde ela está. Ex.: `../garimpai-marca/` (repositório irmão). Se este harness não produz peça, escreva "não se aplica".>

## Quem trabalha dentro
| Pessoa | Papel aqui | O que pode | O que não vê |
|---|---|---|---|
| <nome> | <produz · aprova · lê> | <pastas e ações> | <o que fica fora> |

## De onde bebe (fontes)
| Fonte | Tipo | Como chega |
|---|---|---|
| <ex.: Google Ads> | plataforma por API | <MCP / conector / export> |
| <ex.: criativos do harness social> | outro harness | lê `../garimpai-social/saida/criativos/` |
| <ex.: planilha de verba> | arquivo neste repositório | `dados/verba.md` |

## Skills permitidas
Só as listadas em `skills-permitidas/`. Se uma tarefa pede uma skill que não está lá, a resposta é "este harness não faz isso", não "vou procurar outra".

## Peças deste harness
- **Agentes:** <papel · o que vê · quem confere. Ex.: analista (lê e propõe) · executor (aplica só o aprovado) · verificador (contexto separado, nunca é o executor)>
- **Loops:** <nome · gatilho · o que escreve. Ex.: loop-trafego · diário 7h · `saida/relatorio-diario.md`>
- **Templates:** <ex.: nomenclatura de campanha · relatório semanal · arquivo de aprovação>

## A fila de aprovação
Toda ação para fora ou irreversível (subir campanha, pausar, publicar, enviar, pagar) nasce como arquivo em `aprovar/`, no formato de `aprovar/README.md`. A ação só acontece quando o arquivo está em `aprovado/` com o nome de quem aprovou e a data. O verificador confere, em contexto separado, que o que foi feito é o que foi aprovado.

## Custo
<Quem paga o token de cada uso. Ex.: loops no Actions com `ANTHROPIC_API_KEY` da empresa e teto mensal; chat com a assinatura de quem está no teclado. Ver `docs/quem-paga-o-token.md`.>

## O que este harness nunca faz
- <Ex.: não lê nada fora deste repositório e das fontes listadas>
- <Ex.: não envia e-mail, não publica, não paga, sem arquivo em `aprovado/`>
- Não faz push em `main` a partir de rotina: rotina abre PR.

## O que o Claude erra aqui
- <preenche conforme acontecer: erro repetido duas vezes vira uma linha>
