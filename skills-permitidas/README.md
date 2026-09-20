# skills-permitidas/ · o que este harness pode invocar

Um arquivo por skill, com o nome exato dela e o que ela faz **aqui**. O Claude só usa skill listada nesta pasta. Se a tarefa pede outra coisa, a resposta é "este harness não faz isso".

Exemplo, `relatorio-que-traduz.md`:

```markdown
skill: mentoria:relatorio-que-traduz
para que serve aqui: transformar os números de saida/relatorio-diario.md em três frases que o sócio entende
quando roda: toda manhã, pelo loop-trafego, e sob demanda
nunca: inventar número que não está no relatório de origem
```
