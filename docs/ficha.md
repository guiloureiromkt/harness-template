# A ficha do harness (10 campos)

Preencha antes de mexer em qualquer arquivo. Ela é o `intent` do harness: se você tem o cycle instalado, ela vira `intent/<nome>.md` quase sem edição. A skill `mentoria:harness` faz as perguntas por você.

| Campo | A pergunta | Exemplo (mídia paga) |
|---|---|---|
| **1. Propósito** | O que este harness faz, para quem, e o que nunca faz? | Opera a mídia paga da Garimp.ai. Não produz criativo. |
| **2. Método** | Onde entra o ciclo e onde entra o graph? Que portões este harness pede (dinheiro · permissão · dado destrutivo · superfície de usuário)? | Cycle aqui dentro. Portão de dinheiro: verificador separado. Graph a cada 4 semanas. |
| **3. Peças** | O que vira template, skill, loop e agente? (template: custa zero · skill: rodou 3× na mão sem mudar · loop: skill que rodou 3× sem correção · agente: precisa não ver o resto, ou confere outro) | Agentes: analista, executor, verificador. Loops: diário e semanal. |
| **4. Comprar ou construir** | O que já existe pronto e passa nos 4 gates (serve · licença comercial · não inunda · não roda código obscuro)? O que é seu e ninguém tem? | Instala MCP do Google Ads e do Meta. Constrói nomenclatura e relatório na sua língua. |
| **5. Fontes** | De onde bebe: arquivo no repositório, plataforma por API, outro harness (só a pasta `saida/` dele)? | Ads por MCP, verba em arquivo, criativos de `../garimpai-social/saida/`. |
| **6. APIs e conectores** | Quais são necessários e quais têm caminho grátis? | Todos grátis. Meta: liberar só a conta certa. |
| **7. Interface** | Como a pessoa usa: chat na pasta · pasta de aprovação · portal com MCP? | Chat + `aprovar/`. Sem portal. |
| **8. Hospedagem** | Onde mora: repositório, Actions, máquina, VPS, Drive? | Repositório privado + Actions. |
| **9. Acesso e permissão** | Quem entra, o que pode, o que é bloqueado (três camadas)? | Só o Eduardo. |
| **10. Custo e operação** | De quem é o token em cada uso? Qual a rotina, o que é automático, o que espera aprovação? | Actions com chave da empresa e teto. Nada sobe sem `aprovado/`. |
