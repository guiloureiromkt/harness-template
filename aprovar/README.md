# aprovar/ · a fila de aprovação

> A skill que opera esta fila é a `mentoria:fila-de-aprovacao` (instala com `/plugin install mentoria@mentoria-skills`): ela propõe, executa só o aprovado e chama um verificador em contexto separado. `python3 <caminho-da-skill>/scripts/fila.py` lista a fila sem gastar token.

Todo arquivo aqui é um pedido de ação para fora, escrito por um loop ou por um agente. Ninguém executa nada a partir desta pasta.

## Formato do arquivo

Nome: `AAAA-MM-DD-<verbo>-<objeto>.md`. Ex.: `2026-10-03-pausar-conjunto-remarketing.md`.

```markdown
---
acao: pausar conjunto de anúncios
alvo: Meta · conta Garimp.ai · conjunto "remarketing 30d"
proposto_por: loop-trafego · 2026-10-03 07:12
motivo: CPA de R$ 41 contra teto de R$ 25 por 3 dias seguidos (relatório: saida/relatorio-diario.md, 2026-10-03)
reversivel: sim, reativar o conjunto
prazo: se ninguém responder até 2026-10-04 18h, nada acontece
---

## O que vai ser feito, exatamente
1. …
2. …

## O que NÃO vai ser feito
- …
```

## Como aprovar

A pessoa que aprova **move o arquivo para `aprovado/`** e acrescenta no fim:

```markdown
aprovado_por: Eduardo · 2026-10-03 14:20
```

Só com o arquivo em `aprovado/` o executor age. Depois, o verificador (contexto separado, nunca o executor) escreve abaixo o que conferiu:

```markdown
verificado_por: verificador · 2026-10-03 14:31 · conjunto pausado, print em saida/evidencias/…
```

Arquivo que ninguém aprovou até o prazo fica aqui como registro e não é executado.
