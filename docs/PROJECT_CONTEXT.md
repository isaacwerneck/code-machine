# Contexto geral — Product Factory

## Visão do fundador

Criar renda adicional com produtos digitais desenvolvidos individualmente e apoiados por IA. A ambição de longo prazo é uma **fábrica de software** capaz de descobrir demandas, especificar, criar, testar, publicar e acompanhar produtos, com regras, padrões de qualidade, design e negócio estabelecidos pelo fundador. O objetivo inicial **não é autonomia plena**: é encontrar um primeiro produto com demanda e montar a fundação técnica/documental reproduzível.

O fundador aceita que a evolução comercial possa exigir meses (foi mencionado horizonte de 3, 6, 9 ou 12 meses), pretende agir com persistência, mas **não deve assumir retorno financeiro garantido**. Medir aprendizado e limitar exposição financeira é importante.

## Conhecimentos e modo de trabalhar

- Desenvolvedor e estudante de Análise e Desenvolvimento de Sistemas perto da conclusão; experiência em engenharia de software.
- Familiaridade principal: **JavaScript e Node.js**; flexível quanto a outras tecnologias. Sintaxe pode ser menos fluente que arquitetura e lógica.
- Usa prompts detalhados para IA gerar código; cria bases, define requisitos, revisa e corrige. Usa **Codex** no computador e tem acesso ao **ChatGPT Plus**; relatou uma assinatura paga do Gemini (identificar modalidade exata).
- Estuda **design** e presta atenção em interface/qualidade visual.
- Trabalha há cerca de três anos com **CRM, HubSpot, código e automações**, possuindo conhecimento de processos comerciais, funis e marketing.
- Também é **produtor musical**; isto pode ser útil para nichos futuros (ferramentas para produtores, criadores e áudio), mas não é foco obrigatório.
- Tem facilidade em idealização de produtos e produtividade, segundo seu relato.

## Problema de distribuição

O fundador não conta com rede próxima de contatos para entrevistar ou conseguir primeiros compradores. Prefere inicialmente **pesquisa online, investigação de reclamações e demanda existente, venda por licença via marketplace e demonstrações públicas**. Não exigir entrevistas presenciais ou conhecidos como pré-requisito. Conversas com desconhecidos e entrevistas online podem ser opção, mas não precisam bloquear a primeira experiência.

## Sequência estratégica escolhida

1. **Pesquisar** demandas, concorrentes, problemas de clientes e produtos vendidos, com IA e evidências.
2. **Escolher e desenvolver** um MVP pequeno, usando IA e documentação contínua.
3. **Publicar/distribuir** nas plataformas adequadas ao formato de produto; preferir licença no primeiro teste, sem descartar SaaS/assinaturas.
4. **Medir feedback**: visualizações, demonstrações, conversões, compras, reembolsos, reclamações e solicitações.
5. **Construir a fábrica e o conhecimento em paralelo**: padrões, prompts, componentes, decisões e um app que seleciona perfis de IA. A autonomia aumenta só após estabilidade e validação.

## Primeiro produto comercial — ainda hipótese

Candidato principal discutido: **gerador de orçamentos/propostas profissionais em PDF** para prestadores de serviço (por exemplo eletricistas, freelancers, fotógrafos e profissionais locais). MVP possível: catálogo de serviços/materiais, dados de cliente, cálculos, modelos, logo/identidade visual e exportação PDF. Pode ser licenciado e evoluir para variantes por profissão com núcleo reaproveitável. Faixa de preço **hipotética**, discutida: R$ 49–99 por licença (a testar, não preço de mercado comprovado).

Candidato alternativo estrategicamente forte: **ferramenta de CRM/HubSpot** (auditoria, limpeza de dados, relatórios, diagnósticos de workflows, sincronizações, mini-CRM, integrações), aproveitando experiência específica do fundador. Comparar com gerador PDF antes de declarar vencedor. Não reutilizar material confidencial do empregador.

## Visão da aplicação interna (V0.1)

- Criar repositório `product-factory`/`fabrica` no GitHub.
- Fazer um app local com **uma janela/interface simples**; o fundador cogitou **Raylib com bindings para Node.js** como opção por familiaridade. Verificar compatibilidade exata de biblioteca, sistema operacional e manutenção antes de firmar essa escolha. Electron ou web local são alternativas.
- Selecionar papel/profissão `Pesquisador` ou `Desenvolvedor`.
- Escrever prompt/tarefa num campo.
- Backend Node.js identifica papel, carrega instruções específicas e opcionalmente documentos de contexto.
- Backend chama a **Gemini API** (inicialmente por custo e acesso), recebe resultado e mostra na interface; idealmente estrutura JSON quando for necessário dividir em seções.
- Guardar tarefas, resultados e histórico em JSON ou SQLite; versionar documentação no GitHub.
- Sem necessidade de Codex para escrever o programa; Codex pode acelerar desenvolvimento, mas não é requisito.

## Conceitos de IA consolidados

- **Modelo:** IA disponível por API ou executada localmente.
- **Perfil/role:** instruções específicas e eventualmente lista de ferramentas; papéis diferentes podem compartilhar o mesmo modelo.
- **Agente propriamente dito:** loop controlado que pode chamar ferramentas, receber resultados, manter estado e decidir próximos passos.
- **Orquestrador:** programa que coordena execução, armazenamento, permissões, custos, estados e aprovações.
- **Conhecimento:** arquivos Markdown, exemplos e componentes reaproveitáveis; fornecidos ao modelo em contexto ou recuperados sob demanda. Isso não altera permanentemente os pesos do modelo.
- **Treinamento/fine-tuning:** opcional no futuro; não necessário para a fase inicial.

## Considerações comerciais

- Marketplace não garante tráfego ou vendas; escolher o canal adequado ao formato, título, demonstração e nicho.
- Distribuição e marketing são tão importantes quanto geração de código.
- Começar com um problema delimitado e um público específico; uma primeira venda de desconhecido é um marco valioso, não precisa começar com 100 clientes.
- Não confundir visitas, buscas e pedidos de orçamento com compras comprovadas.
- Priorização orientada a evidência, custo de execução, diferenciação e intenção de compra.

## Decisões não fechadas

- Biblioteca e sistema operacional da interface; se haverá desktop nativo ou web local.
- Modelo Gemini específico, cotas gratuitas, custos e eventual crédito da assinatura (verificar diretamente na conta e docs atuais).
- Primeiro produto vencedor (PDF vs CRM); plataforma principal de venda; modelo de licença e política de suporte.
- Estrutura precisa de schemas, persistência e quando conectar ferramentas reais.

Leia `docs/DECISIONS.md` para status detalhado.
