# Acesso e permissão: as três camadas

O harness é fechado por três travas, uma dentro da outra. Nenhuma precisa ser inventada.

## 1 · Quem entra (o repositório)
Permissão do GitHub. Quem trabalha dentro é colaborador **deste** repositório e de nenhum outro. A Fabi do social não vê o repositório da mídia paga porque não está nele, e pronto.

## 2 · O que o Claude pode fazer aqui dentro (o `.claude/settings.json`)
A lista de permitidos e negados deste repositório. O padrão do template nega: ler fora da pasta, ler segredo, push em `main`, comando destrutivo, acessar a web. Cada harness tira da lista só o que precisa. O `CLAUDE.md` completa: só as skills em `skills-permitidas/`.

## 3 · O que o mundo permite (o MCP e os segredos)
O MCP de cada sistema define o escopo: o do Gmail que lê e redige mas não dispara, o do Google Ads que só lê, o do Meta que cria campanha (por isso ele só entra no harness de mídia). Os segredos (chaves, tokens) ficam nos *secrets* do repositório, um conjunto por harness: o harness social não tem a chave do banco.

## O teste de alcance
Antes de dizer que uma pessoa "está dentro" do harness: ela abriu, viu o que devia, tentou ver o que não devia e não conseguiu. Os três, na frente de quem construiu. Sem isso, a permissão é teoria.
