# Template de harness

**Um harness é uma pasta fechada para um propósito só.** Dentro dela ficam só os agentes, as skills, os loops, os dados e as pessoas daquele trabalho; o resto do teu segundo cérebro não entra. Este repositório é o esqueleto de um harness: você clona, preenche quatro arquivos e já tem o ambiente pronto para construir com o Claude Code, sem a IA se perder no que não é dela.

Ele existe porque montar o esqueleto não ensina nada e custa uma tarde. O que ensina é decidir o que vai dentro, e isso continua sendo teu.

---

## O que vem aqui

| Arquivo ou pasta | Para que serve | Você preenche? |
|---|---|---|
| `CLAUDE.md` | O arquivo mãe do harness: propósito, quem trabalha dentro, de onde bebe, quais skills pode usar, e a regra de quem lê este arquivo (construção × rotina) | **Sim**, é o principal |
| `.claude/settings.json` | O que o Claude pode e não pode fazer aqui (ferramentas, comandos, pastas). É a permissão em código | **Sim**, revisa a lista de negados |
| `aprovar/` e `aprovado/` | A fila de aprovação: o loop deixa o que quer fazer em `aprovar/`, uma pessoa escreve "aprovado" e move; só então a ação acontece | Não, só usa |
| `saida/` | O que este harness publica para os outros lerem. Outro harness nunca lê o teu repositório inteiro, só esta pasta | Não, só usa |
| `skills-permitidas/` | Um arquivo por skill do teu arsenal que este harness pode invocar, com o que ela faz aqui | **Sim**, uma linha por skill |
| `.github/workflows/loop-exemplo.yml` | Um loop de tempo de exemplo: roda em horário marcado, escreve em `saida/`, abre PR. Não faz push em `main` | Copia e adapta |
| `docs/quem-paga-o-token.md` | A regra de custo: quem aperta o botão paga com a chave do harness, não com a assinatura de quem construiu | Lê uma vez |
| `docs/acesso-e-permissao.md` | As três camadas de acesso (repositório · Claude · mundo) e onde cada uma se configura | Lê uma vez |

## Como usar

1. **Clona como template.** No GitHub, botão *Use this template*, repositório **privado**, com o nome do harness (`garimpai-midia`, `garimpai-social`, `conciliacao`).
2. **Preenche a ficha antes de mexer em qualquer arquivo.** Se você tem a skill `mentoria:harness` instalada, roda `/mentoria:harness` dentro da pasta: ela pergunta os dez campos e escreve o `CLAUDE.md` e o `intent/` para você. Se não tem, a ficha está em `docs/ficha.md`, preenche na mão.
3. **Revisa `.claude/settings.json`.** A lista de negados vem restritiva de propósito. Tira o que este harness precisa de verdade, e só isso.
4. **Liga o ciclo aqui dentro, nunca no workspace.** `/cycle:init` roda nesta pasta. Os teus loops de outros projetos moram ao lado deste repositório, nunca embaixo dele.
5. **Convida as pessoas.** Quem trabalha dentro entra como colaborador deste repositório e de nenhum outro.

## O que este template não é

Não é o teu Command Center. É uma peça dele. Cada harness é uma cópia deste esqueleto com propósito, gente e dados próprios. O que os harnesses compartilham (skills, agentes, templates) mora no teu **arsenal**, um repositório de skills publicado como plugin, e cada harness lista em `skills-permitidas/` as que pode usar.

## Licença

MIT. Feito por Gui Loureiro para a Mentoria Mão na Massa. Usa, copia, adapta.
