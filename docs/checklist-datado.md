# O mês como checklist datado

Um loop de execução mensal (conciliação, fechamento, cobrança) não precisa de código: precisa do **mês escrito como lista de passos com dia marcado**, e de um loop diário que lê a lista, faz o passo do dia e para onde uma pessoa tem que agir. Este arquivo é o modelo. Copie para `conciliacao/AAAA-MM.md` (ou o nome da sua rotina) e preencha.

Regras que valem para todo passo:
- **Cada passo diz o que lê, o que escreve, onde deixa a evidência, e se roda sozinho ou para.**
- **Passo que paga, transfere ou reembolsa nunca roda sozinho.** O loop prepara (baixa, confere, calcula) e entra na fila de aprovação; a pessoa paga.
- **Nunca apaga, nunca envia.** E-mail, mensagem e cobrança saem como rascunho em `saida/rascunhos/`, para uma pessoa mandar.
- **Feito é feito com evidência**: o arquivo baixado, o cruzamento em `saida/`, o print. Sem evidência, o passo fica aberto.

## Exemplo preenchido: conciliação de outubro (Garimp.ai, adaptar)

```markdown
# Conciliação · 2026-10

| dia | passo | lê | escreve | sozinho? | evidência | feito |
|---|---|---|---|---|---|---|
| 01 | Baixar os boletos do frete do mês anterior | e-mail (rótulo `frete`) · portal da transportadora | `docs/frete/2026-09/*.pdf` | sim | os PDFs | [ ] |
| 01 | Baixar os e-mails de nota fiscal recebidos em setembro | e-mail (busca `NF` ou `nota fiscal`, setembro) | `docs/nf/2026-09/*.pdf` + `docs/nf/2026-09/indice.md` (número, emissor, valor, data) | sim | o índice | [ ] |
| 02 | Exportar o extrato do provedor de pagamento (PagBank e Stone) | painel do provedor (export manual até ter API) | `dados/extrato-2026-09.csv` | **não**: uma pessoa exporta e coloca o arquivo | o CSV | [ ] |
| 03 | Cruzar vendas da plataforma × extrato do provedor | `dados/vendas-2026-09.csv` · `dados/extrato-2026-09.csv` | `saida/conciliacao-2026-09.md` (o que bate, o que não bate, com id e valor) | sim | o arquivo de saída | [ ] |
| 03 | Listar as divergências e direcionar | `saida/conciliacao-2026-09.md` | `saida/rascunhos/2026-09-divergencias-<area>.md`, um por área (operações · tecnologia · marketing) | sim, mas **não envia** | os rascunhos | [ ] |
| 05 | Calcular o repasse de cada brechó (split) | `dados/vendas-2026-09.csv` · `dados/regras-repasse.md` | `saida/repasses-2026-09.md` (por brechó: vendas, taxa, repasse) | sim | o arquivo | [ ] |
| 05 | Preparar os pagamentos de repasse | `saida/repasses-2026-09.md` | um pedido por lote em `aprovar/` (valor, destinatário, origem) | **para**: dinheiro | o pedido | [ ] |
| 08 | Preparar a folha (funcionários e prestadores) | `dados/folha-2026-09.md` (sigiloso) | pedido em `aprovar/` | **para**: dinheiro | o pedido | [ ] |
| 10 | Preparar o pagamento dos boletos do frete | `docs/frete/2026-09/*.pdf` · NFs correspondentes | pedido em `aprovar/` com boleto + NF conferidos | **para**: dinheiro | o pedido | [ ] |
| 15 | Enviar à contabilidade: NFs, comissões, extrato | `docs/nf/2026-09/` · `saida/repasses-2026-09.md` · extrato | `saida/rascunhos/2026-09-contabilidade.md` (e-mail pronto com anexos listados) | sim, mas **não envia** | o rascunho | [ ] |
| 20 | Conferir impostos do mês (guias e vencimentos) | guias recebidas · calendário fiscal | `saida/impostos-2026-10.md` | sim | o arquivo | [ ] |
| 20 | Preparar o pagamento das guias | `saida/impostos-2026-10.md` | pedido em `aprovar/` | **para**: dinheiro | o pedido | [ ] |
| 28 | Fechar o período: o que ficou aberto e por quê | esta lista | `saida/fechamento-2026-09.md` | sim | o arquivo | [ ] |
```

## A auditoria, com outra frequência

O checklist é a **execução**. A **auditoria** é outro loop, mensal ou trimestral, que só lê: cruza pagamentos, frete, provedor e notas de vários meses, lista as incongruências e escreve um rascunho por área para quem resolve. Ela nunca corrige nada; direciona. Modelo de passo:

```markdown
| trimestre | passo | lê | escreve | sozinho? |
|---|---|---|---|---|
| out–dez | Achar pagamento sem NF, NF sem pagamento, frete cobrado duas vezes, repasse fora da regra | `saida/conciliacao-*.md` dos 3 meses · `docs/nf/` · `docs/frete/` | `saida/auditoria-2026-T4.md` + `saida/rascunhos/auditoria-<area>.md` | sim, não envia |
```
