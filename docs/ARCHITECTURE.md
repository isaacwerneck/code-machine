# Arquitetura técnica — da V0.1 à fábrica de agentes

## Princípio

Começar com app simples que conversa com API; projetar boas fronteiras para crescer. **Um papel especializado não equivale automaticamente a um agente autônomo.**

## V0.1 — fluxo

```text
[Janela / interface local]
   (seleciona papel + escreve prompt)
                |
                v
[Controlador Node.js] --> [Carregar config do papel]
                |         [Carregar knowledge relevante]
                v
      [Provider / Gemini SDK] ----HTTPS----> [Gemini API]
                |
                v
     [Validação / formatação]
                |
         +------+------+
         |             |
     [UI render]   [SQLite/JSON]
```

**Papel selecionado**: `researcher` ou `developer` inicialmente. Cada perfil tem `name`, `systemInstruction`, `allowedTools` (na V0.1, vazia), limites e fontes de conhecimento.

**Backend**: determina papel, compõe mensagens, envia à API, trata timeout/limites/erros, valida resposta, salva execução e devolve UI. Como a interface é local, backend pode ser mesmo processo Node.js ou processo separado; preferir simplicidade.

**Saídas**: texto para chat e, quando necessário, JSON seguindo schema explícito; validar antes de renderizar seções/tabelas. Não confiar no texto como JSON sem validação.

**Estado mínimo de tarefa**: `pending`, `running`, `completed`, `failed`; timestamps e erros sem segredos.

## Interface

O fundador cogitou **Raylib com Node.js** para janela local. **Confirmar a biblioteca exata de bindings, compatibilidade com runtime/OS, manutenção e suporte a campos de texto**. Raylib é originalmente uma biblioteca de jogos/multimídia e pode ser pouco ergonômica para formulários densos; alternativas: Electron, Tauri (com backend Node separado), ou aplicação web local. UI é substituível se desacoplada do core.

## Estrutura inicial sugerida

```text
src/
  ui/
  core/agent-manager.js
  agents/researcher.js
  agents/developer.js
  services/model-provider.js
  persistence/
  index.js
knowledge/
  architecture.md
  design.md
  quality.md
data/      # gitignored, se dados privados
.env       # gitignored
```

A documentação distribuída neste pacote constitui a primeira base de conhecimento. Não crie pastas vazias em excesso até haver uso real.

## API Gemini e opções de modelo

- Preferência inicial: **Gemini API**, usando SDK JavaScript oficial `@google/genai`, por potencial nível gratuito; verificar documentação e modelos **atuais**.
- Google AI Studio permite gerar chave de API em projetos elegíveis.
- **ChatGPT Plus não equivale a franquia genérica da OpenAI API**; Codex via assinatura é ferramenta distinta das chamadas programáticas.
- Assinatura paga do Gemini/Google AI Pro pode oferecer benefícios específicos do Google Developer Program/AI Studio, **não assumir créditos de API, cotas ou valores sem verificar elegibilidade pessoal e documentação atual**.
- Janela de contexto de “1 milhão de tokens” **não significa 1 milhão de tokens gratuitos**; diferenciar contexto, tokens por minuto, requisições por minuto/dia e créditos financeiros.
- Prover configuração de modelo via variável de ambiente; **não hardcode identificador de modelo não verificado**.
- Chave no ambiente, nunca na interface enviada a terceiros nem no GitHub.

## V0.2 — contexto e memória operacional

- Incluir Markdown de instruções, schemas, componentes reutilizáveis e exemplos aprovados.
- Salvar entradas, saídas e avaliações. Começar com JSON/SQLite; PostgreSQL/pgvector apenas quando houver necessidade.
- Registrar o que o fundador corrigiu; converter erros recorrentes em regra, exemplo ou teste automatizado.
- Essa abordagem usa recuperação de contexto, **não treina os pesos da IA**.

## V0.3 — ferramentas (tool calling)

- Pesquisador: busca permitida, leitura de fontes, extração com referências, salvar relatórios.
- Desenvolvedor: ler arquivos do repositório, criar branch, editar arquivos em workspace isolado, executar lint/testes, gerar diff.
- Tools só funcionam se implementadas no programa. A API sozinha não tem acesso automático a GitHub, arquivos ou web.
- Restringir caminho de arquivos, comandos, host de rede e tamanho de respostas. Ferramentas e conteúdos externos são superfície de prompt injection.

## V0.4+ — orquestração

- Múltiplos perfis/papéis colaborando por tarefas explícitas, com passagem de artefatos e validação.
- Agendamento (cron ou n8n), fila de trabalhos, retries com backoff e idempotência, rastreamento de custo/uso.
- Aprovação humana antes de publicar, cobrar, enviar mensagens, fazer deploy, executar mudanças destrutivas ou acessar dados sensíveis.
- Execução local para desenvolvimento; servidor/cloud somente quando precisar rodar continuamente. Modelos remotos via API não rodam no computador local; o **orquestrador** roda localmente. Modelo open-weight local via Ollama é alternativa futura, sujeita a limitações de hardware.

## Possibilidades futuras (não escopo V0.1)

TypeScript, Agents SDK ou outro framework de agentes, n8n, PostgreSQL, Next.js, Docker, CI GitHub, vector search. Adicionar apenas com justificativa operacional. Medir orçamento e uso, inclusive custos de tokens, chamadas de ferramentas, suporte e cloud.
