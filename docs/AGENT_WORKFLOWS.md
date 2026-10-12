# Papéis, fluxos e aprendizagem operacional

## Perfis inicialmente selecionáveis

### Pesquisador (`researcher`)

**Objetivo:** avaliar oportunidades de software e relatórios de evidência.

**Instruções:** diferenciar fatos, hipótese e inferência; descrever segmento, problema, alternativas, evidências com links/datas, preço estimado, risco e validação; nunca inventar vendas, dados de pesquisa ou ter realizado buscas não executadas.

**Entrada V0.1:** prompt + dados fornecidos pelo usuário + arquivos de contexto. **Não** tem acesso web automático nessa versão.

**Saída sugerida:** `{summary, problem, audience, evidence, competitors, value_proposition, risks, validation_steps, confidence}`.

### Desenvolvedor (`developer`)

**Objetivo:** criar planos de arquitetura e implementar software seguindo padrões documentados.

**Instruções:** preferir Node.js/TypeScript quando apropriado, foco em simplicidade e testes, separar core/UI/serviços, não afirmar execução ou testes fictícios.

**Entrada V0.1:** prompt + padrões de engenharia/arquitetura. **Não** escreve no filesystem até que ferramentas seguras sejam adicionadas.

**Saída:** plano, arquivos sugeridos, código quando pedido, testes e ressalvas.

## Futuros papéis

- **Product agent:** transformar evidências em PRD e critérios de aceitação.
- **Designer:** fluxos e padrões visuais/acessibilidade.
- **QA:** testes, análise de segurança, verificação contra requisitos.
- **Comercial:** rascunhos de anúncios, descrições, páginas, preços como hipóteses; ações externas só com aprovação.
- **Feedback analyst:** agrupar reclamações, bugs, métricas e oportunidades de melhoria.

Um modelo pode sustentar vários papéis com diferentes system prompts, contextos e ferramentas. Não é necessário treinar modelos independentes nem manter seis processos distintos.

## Ciclo de vida de uma tarefa

1. Usuário seleciona perfil e envia instrução.
2. Orquestrador atribui ID, grava estado `pending` e configura limites.
3. Carrega prompt de sistema e contexto relevante; registra versões de instrução e modelo.
4. Envia à API; responde a falhas transitórias dentro de limite definido.
5. Quando ferramentas existirem, modelo solicita ferramenta; sistema confere permissão, executa e devolve resultado; repete sob limites.
6. Valida schema/saída, guarda resultado e marca `completed` ou `failed`.
7. Usuário avalia utilidade, registra correções e aprova passos críticos.
8. Padrões corrigidos viram documentação, exemplos ou testes, não apenas mensagens perdidas no chat.

## Quando surgir autonomia real

```text
Pesquisa -> Avaliação -> [APROVAÇÃO] -> PRD -> Implementação
-> Testes/revisão -> [APROVAÇÃO] -> Publicação -> Feedback
```

Pesquisa contínua, publicação comercial e comunicação com clientes exigem checagem de permissões/termos. Não atribuir autonomia irrestrita. Limitar custo, duração, acesso e retries.

## Template de evento de aprendizado

```yaml
id: learn-001
date: YYYY-MM-DD
project: pdf-quotations
agent_role: developer
problem: "Regra de negócio misturada à UI"
original_behavior: "..."
correction: "Mover cálculo para service puro e testável"
new_rule_or_test: "knowledge/ENGINEERING_STANDARDS.md"
status: proposed
```

Os eventos devem ser revisados; uma correção única não é automaticamente uma regra universal.
