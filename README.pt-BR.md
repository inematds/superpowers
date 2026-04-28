# Superpowers

Superpowers é uma metodologia completa de desenvolvimento de software para seus agentes de código, construída sobre um conjunto de skills composáveis e algumas instruções iniciais que garantem que seu agente as utilize.

## Como funciona

Tudo começa no momento em que você inicializa seu agente de código. Assim que ele percebe que você está construindo algo, ele *não* simplesmente sai escrevendo código. Em vez disso, ele dá um passo atrás e pergunta o que você realmente quer fazer.

Depois de extrair uma especificação da conversa, ele a apresenta em partes pequenas o suficiente para você ler e absorver de verdade.

Após você aprovar o design, seu agente monta um plano de implementação claro o bastante para ser seguido por um engenheiro júnior entusiasmado, sem bom gosto, sem julgamento, sem contexto do projeto e com aversão a testes. O plano enfatiza TDD verdadeiro com ciclo vermelho/verde, YAGNI (You Aren't Gonna Need It) e DRY.

Em seguida, quando você diz "vai", ele inicia um processo de *desenvolvimento orientado a subagentes*, fazendo com que agentes trabalhem em cada tarefa de engenharia, inspecionando e revisando o trabalho deles, e avançando. Não é raro o Claude conseguir trabalhar autonomamente por algumas horas sem desviar do plano que você elaborou.

Tem muito mais coisa, mas esse é o núcleo do sistema. E como as skills são ativadas automaticamente, você não precisa fazer nada especial. Seu agente de código simplesmente tem Superpowers.


## Patrocínio

Se o Superpowers te ajudou a fazer coisas que geram dinheiro e você estiver disposto, ficaria muito grato se considerasse [patrocinar meu trabalho opensource](https://github.com/sponsors/obra).

Obrigado!

- Jesse


## Instalação

**Nota:** A instalação varia conforme a plataforma.

### Marketplace Oficial do Claude Code

O Superpowers está disponível no [marketplace oficial de plugins do Claude](https://claude.com/plugins/superpowers).

Instale o plugin pelo marketplace oficial da Anthropic:

```bash
/plugin install superpowers@claude-plugins-official
```

### Claude Code (Marketplace do Superpowers)

O marketplace do Superpowers oferece o Superpowers e outros plugins relacionados para o Claude Code.

No Claude Code, registre o marketplace primeiro:

```bash
/plugin marketplace add obra/superpowers-marketplace
```

Depois instale o plugin desse marketplace:

```bash
/plugin install superpowers@superpowers-marketplace
```

### OpenAI Codex CLI

- Abra a interface de busca de plugins

```bash
/plugins
```

Busque por Superpowers

```bash
superpowers
```

Selecione `Install Plugin`

### OpenAI Codex App

- No aplicativo Codex, clique em Plugins na barra lateral.
- Você verá `Superpowers` na seção Coding.
- Clique no `+` ao lado do Superpowers e siga as instruções.


### Cursor (via Plugin Marketplace)

No chat do Cursor Agent, instale pelo marketplace:

```text
/add-plugin superpowers
```

ou busque por "superpowers" no marketplace de plugins.

### OpenCode

Diga ao OpenCode:

```
Fetch and follow instructions from https://raw.githubusercontent.com/obra/superpowers/refs/heads/main/.opencode/INSTALL.md
```

**Documentação detalhada:** [docs/README.opencode.md](docs/README.opencode.md)

### GitHub Copilot CLI

```bash
copilot plugin marketplace add obra/superpowers-marketplace
copilot plugin install superpowers@superpowers-marketplace
```

### Gemini CLI

```bash
gemini extensions install https://github.com/obra/superpowers
```

Para atualizar:

```bash
gemini extensions update superpowers
```

## O Fluxo de Trabalho Básico

1. **brainstorming** - Ativado antes de escrever código. Refina ideias brutas através de perguntas, explora alternativas e apresenta o design em seções para validação. Salva o documento de design.

2. **using-git-worktrees** - Ativado após aprovação do design. Cria um workspace isolado em um novo branch, executa o setup do projeto e verifica uma baseline limpa de testes.

3. **writing-plans** - Ativado com o design aprovado. Divide o trabalho em tarefas pequenas (2 a 5 minutos cada). Cada tarefa tem caminhos de arquivo exatos, código completo e etapas de verificação.

4. **subagent-driven-development** ou **executing-plans** - Ativado com o plano. Despacha um novo subagente por tarefa com revisão em dois estágios (conformidade com a spec e depois qualidade do código), ou executa em lotes com checkpoints humanos.

5. **test-driven-development** - Ativado durante a implementação. Aplica o ciclo VERMELHO-VERDE-REFATORAR: escrever teste que falha, ver ele falhar, escrever código mínimo, ver ele passar, commitar. Deleta código escrito antes dos testes.

6. **requesting-code-review** - Ativado entre tarefas. Revisa em relação ao plano e reporta problemas por severidade. Problemas críticos bloqueiam o progresso.

7. **finishing-a-development-branch** - Ativado quando as tarefas são concluídas. Verifica os testes, apresenta opções (merge/PR/manter/descartar) e limpa a worktree.

**O agente verifica as skills relevantes antes de qualquer tarefa.** Fluxos obrigatórios, não sugestões.

## O Que Está Incluído

### Biblioteca de Skills

**Testes**
- **test-driven-development** - Ciclo VERMELHO-VERDE-REFATORAR (inclui referência de antipadrões de teste)

**Debugging**
- **systematic-debugging** - Processo de causa raiz em 4 fases (inclui técnicas de rastreamento de causa raiz, defesa em profundidade e espera baseada em condições)
- **verification-before-completion** - Garante que o problema foi realmente corrigido

**Colaboração**
- **brainstorming** - Refinamento de design socrático
- **writing-plans** - Planos de implementação detalhados
- **executing-plans** - Execução em lotes com checkpoints
- **dispatching-parallel-agents** - Fluxos de trabalho com subagentes concorrentes
- **requesting-code-review** - Checklist pré-revisão
- **receiving-code-review** - Respondendo ao feedback
- **using-git-worktrees** - Branches de desenvolvimento paralelo
- **finishing-a-development-branch** - Fluxo de decisão merge/PR
- **subagent-driven-development** - Iteração rápida com revisão em dois estágios (conformidade com a spec e qualidade do código)

**Meta**
- **writing-skills** - Crie novas skills seguindo as melhores práticas (inclui metodologia de teste)
- **using-superpowers** - Introdução ao sistema de skills

## Filosofia

- **Desenvolvimento Orientado a Testes** - Escreva testes primeiro, sempre
- **Sistemático ao invés de ad-hoc** - Processo ao invés de adivinhação
- **Redução de complexidade** - Simplicidade como objetivo principal
- **Evidência ao invés de afirmações** - Verifique antes de declarar sucesso

Leia [o anúncio original de lançamento](https://blog.fsck.com/2025/10/09/superpowers/).

## Contribuindo

O processo geral de contribuição para o Superpowers está abaixo. Tenha em mente que geralmente não aceitamos contribuições de novas skills e que qualquer atualização de skills deve funcionar em todos os agentes de código que suportamos.

1. Faça um fork do repositório
2. Mude para o branch 'dev'
3. Crie um branch para o seu trabalho
4. Siga a skill `writing-skills` para criar e testar skills novas e modificadas
5. Envie um PR, tendo o cuidado de preencher o template de pull request

Veja `skills/writing-skills/SKILL.md` para o guia completo.

## Atualizando

As atualizações do Superpowers dependem um pouco do agente de código, mas geralmente são automáticas.

## Licença

Licença MIT — veja o arquivo LICENSE para detalhes.

## Comunidade

O Superpowers é construído por [Jesse Vincent](https://blog.fsck.com) e o restante da equipe da [Prime Radiant](https://primeradiant.com).

- **Discord**: [Junte-se a nós](https://discord.gg/35wsABTejz) para suporte da comunidade, perguntas e para compartilhar o que você está construindo com o Superpowers
- **Issues**: https://github.com/obra/superpowers/issues
- **Anúncios de lançamento**: [Cadastre-se](https://primeradiant.com/superpowers/) para ser notificado sobre novas versões
