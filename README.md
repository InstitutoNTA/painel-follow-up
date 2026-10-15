# Painel de Follow-up

Painel do time de **Sucesso do Aluno da Pós-graduação** para acompanhar alunos com pendências de matrícula (não acessou a plataforma, não assinou o contrato, não subiu a documentação) e preparar mensagens de follow-up para o WhatsApp.

## Onde usar

| Versão | Para quê | O agente escreve as mensagens? | Onde os dados ficam |
|---|---|---|---|
| **Painel no Claude** (link compartilhado pelo Otacílio) | Uso diário do time | Sim | Salvos no painel, iguais para todo o time |
| **GitHub Pages** (este repositório) | Consulta, testes e evolução do código | Não | Só no navegador de quem abriu |

> Para o uso do dia a dia, use o link do painel no Claude. Esta cópia no GitHub serve para o time ver, sugerir e editar o código.

## O que o painel faz

- **Painel do dia:** quadros de resumo clicáveis (em acompanhamento, sem contrato, sem documentação, nunca acessou, vencendo ou vencido, mensagens pendentes hoje e pendências resolvidas), filtro por pós-graduação e tabela ordenada por dias em aberto.
- **Cadastro do aluno:** nenhum campo é obrigatório. Dados, pendências, perfil (transição ou especialização), dor principal, pós e observações.
- **Acompanhamento:** mensagem de hoje com escolha de tom (Acolhedor, Lembrete, Firme, Urgente), instrução opcional para ajustar o texto, copiar, marcar como enviada, respostas do aluno e histórico.
- **Configurações:** quem assina, prazo (padrão 7 dias) e links do passo a passo.

## Regras principais

- **Tom sugerido** (prazo P): primeira mensagem = Acolhedor; abaixo de P/2 = Acolhedor; abaixo de P = Lembrete; até P + 7 = Firme; acima disso = Urgente.
- **Mensagens automáticas:** de segunda a sexta, a partir das 9h, quando o painel é aberto. No máximo uma mensagem por aluno por dia.
- **Saída do acompanhamento:** só quando todas as pendências marcadas forem resolvidas. Responder não tira o aluno do acompanhamento.
- **Nunca citar o nome da empresa.** O time se apresenta como "Sucesso do Aluno da Pós-graduação em [pós]".

## Como editar

Tudo está em um único arquivo: `index.html` (HTML, CSS e JavaScript, sem frameworks).

1. Abra `index.html` aqui no GitHub e clique no ícone de lápis (**Edit this file**).
2. Faça a alteração.
3. Em **Commit changes**, descreva em uma frase o que mudou (ex.: "Ajusta texto do tom Firme").
4. Para mudanças maiores, escolha **Create a new branch** e abra um *pull request* para revisão.

Onde mexer com mais frequência dentro do `index.html`:

- `const POS` — lista de pós-graduações.
- `const PEND` — tipos de pendência e o que o aluno precisa fazer.
- `function montarPrompt` — regras e guia de tons que o agente segue para escrever as mensagens.
- `function tomSugerido` — regra de escolha do tom.
- Bloco `:root` no início do `<style>` — cores do painel.

Depois de editar aqui, avise o Otacílio para atualizar também o painel no Claude.
