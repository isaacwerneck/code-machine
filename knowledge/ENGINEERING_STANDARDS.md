# Padrões iniciais de engenharia e produto

> Proposta para ser refinada conforme o fundador desenvolve produtos reais. **Não confundir preferência inicial com política imutável.**

## Arquitetura

- Separar UI, lógica de negócio, integração com modelos, persistência e acesso a serviços externos.
- Interfaces de serviços pequenas e testáveis; dependências substituíveis para trocar Gemini por outro modelo ou UI sem reescrever o core.
- Evitar complicação prematura: sem microservices, vector DB ou filas distribuídas na V0.1.
- Parametrizar prompts de papel, modelo e regras de saída; versionar mudanças significativas.

## Código

- Priorizar legibilidade, funções com responsabilidade clara, tratamento explícito de erros e nomes coerentes.
- Validar inputs e outputs; esquemas formais quando formatos estruturados forem necessários.
- Não produzir código ficticiamente testado; escrever testes proporcionais às responsabilidades.
- Bibliotecas e versões devem ser confirmadas na documentação atual; não inventar nomes de modelos, endpoints ou métodos.

## Interface e design

- Começar simples: campo de prompt, seleção de papel, estado de execução, área de resultados, erros e histórico.
- Exibir saídas estruturadas em seções quando houver schema, sem parsing oportunista de texto solto.
- Feedback visual de carregamento/erro; suportar textos longos, seleção e cópia.
- Documentar componentes reutilizáveis, espaçamento, tipografia, cores, acessibilidade e estados vazios quando o design amadurecer.
- Raylib pode ser usado por preferência do fundador, mas avaliar se biblioteca é adequada a UI de formulários.

## Segurança

- Nunca comitar API keys ou documentos sensíveis; `.env` no `.gitignore` e `.env.example` com placeholders.
- Nunca embutir chave de API em cliente distribuído. Para app local pessoal, usar variáveis de ambiente/armazenamento local seguro e tratar acesso ao sistema de arquivos.
- Tratar saídas do modelo e documentos externos como não confiáveis.
- Future tools de filesystem/terminal: allowlist, diretório de trabalho restrito, isolamento, revisão de diffs, aprovações humanas.
- Implementar limites de custo/chamadas e retries, registrar falhas sem vazar prompts ou segredos.
- Respeitar dados de terceiros, LGPD, termos de plataformas e propriedade intelectual. Não trazer materiais confidenciais do emprego em CRM/HubSpot.

## Qualidade

- Testar comportamentos essenciais, erros de autenticação, rede, timeout, cota, resposta vazia/inválida e persitência.
- Para produtos PDF, testar cálculos, arredondamento, impostos aplicáveis se existirem, renderização, caracteres especiais e exportação.
- Registrar o que a IA corrigiu, mas não transformar todo comentário ad hoc em regra universal.
- Documentar critérios de aceitação por produto, não apenas aparência visual.

## Padrão de entrega para cada incremento

1. Escopo e motivação.
2. Arquivos e responsabilidades afetadas.
3. Testes realmente executados e resultados.
4. Limitações conhecidas e próximos passos pequenos.
5. Documentação/decisões alteradas quando necessário.
