# Quem paga o token

A regra numa frase: **quem aperta o botão paga com a chave do harness, não com a assinatura de quem construiu.**

| Onde o Claude roda | Quem paga | Como se configura |
|---|---|---|
| No chat, alguém no teclado (Claude Code, app do Claude) | A assinatura da pessoa. Cada pessoa que trabalha dentro precisa da própria cadeira (plano Team ou individual) | Nada a configurar: é o login dela |
| Num loop no GitHub Actions | A empresa, por uso, com chave de API | Secret `ANTHROPIC_API_KEY` no repositório do harness; teto de gasto na console da Anthropic |
| Num portal ou sistema próprio | A empresa, por uso, com chave de API | Chave no servidor, nunca no navegador |
| Geração de imagem, vídeo, voz (Replicate e afins) | A empresa, créditos por uso | Secret no repositório ou no servidor |

Três coisas que dão errado:
1. **Assinatura pessoal fora do chat.** Não vale. Loop e portal usam chave de API, que é outra conta e outra fatura.
2. **Uma chave para todos os harnesses.** Se vazar, vaza tudo, e a fatura não diz quem gastou. Uma chave por harness, com nome do harness.
3. **Sem teto.** Loop com bug roda até a fatura avisar. Teto mensal na console antes do primeiro cron.
