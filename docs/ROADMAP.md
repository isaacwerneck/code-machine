# Roadmap incremental

## Macroetapas do negócio

1. Pesquisa de mercado e evidências de demanda.
2. Seleção de nicho, validação leve e criação do MVP.
3. Publicação adequada ao formato e distribuição.
4. Medição de tráfego, vendas, suporte e feedback.
5. Desenvolvimento contínuo da fábrica de IA, documentando do início.

As etapas 1–4 formam ciclo repetível; a 5 acontece em paralelo, inicialmente de forma manual.

## Plano possível do primeiro mês (não promessa de prazo)

| Período indicativo | Trabalho | Saída |
|---|---|---|
| Dias 1–5 | Levantar ~30 oportunidades/produtos/serviços com fontes | Banco de evidências |
| Dias 6–10 | Comparar problemas, concorrentes e sinais de pagamento | Top 3 hipóteses |
| Dias 11–15 | Testar oferta/demonstração e escolher nicho | Hipótese priorizada |
| Dias 16–23 | Implementar MVP pequeno e documentar | Demo funcional |
| Dias 24–30 | Publicar onde adequado, divulgar e medir | Aprendizados comerciais |

É **um roteiro ilustrativo**, sem garantia de ter produto pronto ou vendas em 30 dias. Adaptar a tempo disponível e requisitos de plataforma.

## Roadmap técnico da fábrica

### Fase F0 — Base do repositório
- [ ] Subir este pacote Markdown ao GitHub.
- [ ] Criar `.gitignore`, `.env.example` sem chave real.
- [ ] Verificar binding Raylib/OS ou escolher UI mais apropriada.
- [ ] Escolher versão suportada de Node.js e modelo Gemini realmente disponível.

### Fase F1 — V0.1, interface mínima
- [ ] Interface simples para selecionar Pesquisador/Desenvolvedor.
- [ ] Campo de prompt e botão de execução.
- [ ] Separar configs de roles e provider Gemini.
- [ ] Exibir texto de resposta, status e erros.
- [ ] Salvar histórico de tarefa (JSON ou SQLite).
- [ ] Proteger chave e controlar tamanho de entrada.

### Fase F2 — V0.2, padrões e saída estruturada
- [ ] Carregar Markdown relevante como contexto.
- [ ] Adicionar schemas para relatórios, validação e renderização.
- [ ] Logar versão de instruções/modelo, entradas não sensíveis e feedback.
- [ ] Converter correções recorrentes em documentos/testes.

### Fase F3 — V0.3, ferramentas
- [ ] Pesquisa web por mecanismo permitido com fonte e timestamp.
- [ ] Leitura segura de repositórios/arquivos.
- [ ] Edição e execução de teste em workspace isolado.
- [ ] Autorizações de ferramenta e orçamento por execução.

### Fase F4 — V0.4+, automação controlada
- [ ] Encadear pesquisa -> especificação -> revisão -> desenvolvimento -> testes.
- [ ] Fila de jobs, retries limitados, checkpoints e observabilidade.
- [ ] Operação em cloud se realmente necessário.
- [ ] Publicação e contatos comerciais apenas mediante aprovação.

## Primeiro marco prático

**Do clique até uma resposta persistida**: selecionar `researcher`, fornecer uma tarefa, o Node.js montar o contexto correto, chamar Gemini, mostrar resposta, gravar resultado e permitir revisão. Sem isso, não adicionar seis agentes nem painel grande.

## Definição de sucesso inicial

- Primeiro ciclo técnico reprodutível da fábrica.
- Pesquisa de mercado organizada, com evidências conferíveis.
- Primeiro MVP disponibilizado/demonstrado.
- Primeiros sinais reais de distribuição e, idealmente, primeiro comprador desconhecido.
- Registro do que funcionou e do que não funcionou.
