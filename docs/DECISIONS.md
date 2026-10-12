# Registro de decisões e hipóteses

Legenda: **Confirmada na conversa** = intenção/decisão expressa pelo fundador, não código implementado. **Proposta** = sugestão do assistente ainda não escolhida. **Pendente** = exige teste/escolha. **Hipótese comercial** = demanda ou preço não comprovados.

| Tema | Estado | Registro |
|---|---|---|
| Nome/repositório | Confirmada na conversa | Criar repositório da fábrica no GitHub; nome exato livre (`product-factory` sugerido). |
| Motivação | Confirmada | Desenvolver produtos vendáveis e evoluir para automação com IA. |
| Pesquisa antes da escolha | Confirmada | Começar com fontes de demanda/concorrência; usar ChatGPT/IA como apoio. |
| Documentar desde o início | Confirmada | Registrar arquitetura, design, negócio, erros, correções e feedback. |
| Linguagem principal | Confirmada | JavaScript/Node.js; aberto a outras ferramentas quando justificadas. |
| UI local | Confirmada como intenção | Criar janela/interface com seleção do papel e prompt; Raylib citado como preferência possível. |
| Raylib binding específico | Pendente | Checar pacote, versão, manutenção, Node/OS e adequação a formulários. |
| Profissões iniciais | Confirmada | Pesquisador e Desenvolvedor. |
| Modelo/API | Proposta aceita para exploração | Experimentar Gemini API; conferir chave, modalidade grátis, modelo e limites reais. |
| Gemini Plus/Pro e créditos | Pendente | Verificar qual assinatura existe e benefícios oficiais atuais; não supor créditos ou tokens extras. |
| Dados persistidos | Proposta | Iniciar com arquivos JSON ou SQLite. |
| Saída JSON estruturada | Proposta | Recomendado para dados em painéis, com validação por schema. |
| Primeira automação | Confirmada como direção | App orquestrador simples; sem autonomia de browser, terminal ou deploy na V0.1. |
| Primeiro produto comercial | Hipótese comercial | Gerador de orçamentos PDF, comparar com utilitários CRM/HubSpot. |
| Preço licença PDF | Hipótese comercial | R$ 49–99 discutidos como teste, sem validação. |
| Canais de venda | Pendente | Escolher marketplace compatível e público; não publicar em todas indiscriminadamente. |
| Framework agentes | Proposta futura | Agents SDK, n8n ou LangGraph apenas se necessidades surgirem. |
| Backend/cloud | Pendente/futuro | Começar local; migrar para cloud para execução contínua quando necessário. |
| Controle humano | Princípio recomendado | Aprovar publicação, cobrança, contato com clientes e mudanças sensíveis. |

## Questões para as primeiras sessões de desenvolvimento

1. Qual OS e versão do Node? Que pacote Raylib de Node.js funciona efetivamente nesse ambiente?
2. O programa precisa ser desktop mesmo ou web local serve?
3. Qual modelo Gemini está disponível com a chave do projeto e quais quotas/custos?
4. A primeira resposta será só texto ou precisa de schema JSON com seções?
5. JSON local ou SQLite para histórico inicial?
6. Qual primeiro experimento comercial: PDF por profissão específica ou ferramenta CRM?

## Regra de atualização

Após cada decisão relevante, adicionar data, justificativa, alternativas e impacto; distinguir decisão técnica de resultado de validação comercial.
