# Pesquisa de mercado — síntese de hipóteses e fontes

> **Nota essencial:** esta é a síntese do que foi discutido, não uma nova auditoria independente de números. Indicadores citados em conversas anteriores podem mudar, ter janelas específicas ou não estar verificados aqui; **revalidar diretamente antes de usá-los comercialmente**. Links abaixo são pontos de partida.

## A pergunta certa

Mais útil que "o que mais vende?" é: **"qual problema recorrente as pessoas ou empresas já pagam para resolver, e qual solução pequena posso entregar melhor?"** Produtos campeões de vendas também podem depender de grandes orçamentos de marketing, marca ou distribuição.

## Evidências e sinais mencionados anteriormente

- Estudos e tendências de 2026 em plataformas como Upwork/Fiverr indicaram interesse em integrações de IA, chatbots, automações com n8n e limpeza de dados. **Números percentuais narrados na conversa não devem ser reutilizados sem checagem da fonte, data e metodologia.** São sinais de busca/contratação, **não** faturamento provado de aplicativos.
- Sebrae/E-Commerce Brasil foi citado para a realidade de micro/pequenos negócios com operações digitais geridas por poucos profissionais. Revalidar universo pesquisado, dados e data antes de citar externamente.
- CodeCanyon foi apresentado como ambiente que exibe contagens acumuladas de licenças em certas listagens: exemplos discutidos foram Perfex CRM, MagicAI e ferramentas WhatsApp. **Contagem de vendas, preço e data mudam**. Não inferir receita líquida, assinatura SaaS ou rentabilidade multiplicando preço atual por vendas acumuladas.
- Categorias observadas em comércio de infoprodutos: finanças e negócios, ensino, carreira, saúde/esporte, marketing/vendas. Isso não garante demanda por aplicativos nas mesmas categorias.

## Fontes para consultar

| Objetivo | Fontes |
|---|---|
| Dor e reclamações | https://www.reddit.com ; https://www.reclameaqui.com.br ; https://www.g2.com |
| O que contratam | https://www.workana.com ; https://www.upwork.com ; https://www.fiverr.com |
| Scripts/licenças | https://codecanyon.net ; https://gumroad.com/discover |
| Ecossistemas de apps | https://apps.shopify.com |
| Digital/infoprodutos | https://hotmart.com ; https://kiwify.com.br ; https://www.eduzz.com |
| Necessidades de pequenos negócios | https://sebrae.com.br |

Observar termos, LGPD, regras de API/scraping, recência, metodologia e acesso permitido.

## Modelo de registro por oportunidade

```json
{
  "opportunity_id": "opp-001",
  "problem": "Orçamentos profissionais demoram para ser criados",
  "segment": "Prestadores de serviços",
  "evidence": [
    {"source_url": "", "captured_at": "", "type": "review|job|sale|interview|other", "observation": "", "confidence": "low|medium|high"}
  ],
  "existing_alternatives": [],
  "differentiation_hypothesis": "",
  "price_hypothesis_brl": null,
  "validation_plan": "",
  "status": "researching"
}
```

## Comparação prioritária

**Candidato A — PDF/orçamentos:** mais fácil de demonstrar, baixa infraestrutura, possibilidade de licença e core compartilhado. Verificar concorrência abundante e disposição real a pagar.

**Candidato B — CRM/HubSpot:** vantagem competitiva de conhecimento técnico do fundador; encontrar lacunas de operação, auditorias, integração, limpeza de dados, relatórios ou workflows. Verificar complexidade de integração, termos da HubSpot, privacidade, manutenção e disposição de pagar.

Decidir após pesquisa em um nicho concreto, não por entusiasmo isolado.

## Perguntas que cada pesquisa deve responder

- Quem sofre com esse problema e com que frequência?
- Como resolve hoje e quanto custa (tempo, dinheiro, erro)?
- Qual software/serviço já atende o problema? O que as avaliações negativas revelam?
- Há prova direta de compra/contratação ou apenas buscas/interesse?
- É possível criar uma versão melhor/diferente em dias/semanas?
- Qual o canal de venda viável sem rede pessoal?
- Como demonstrar valor em 30–60 segundos?
- Qual risco legal, privacidade, fraude, suporte ou integração?

## Princípio epistemológico

Classificar tudo em: **fato verificado**, **indício**, **hipótese**, **estimativa** ou **decisão do projeto**. Sempre registrar fonte e data de observação. Não fabricar rankings dos mais vendidos quando a plataforma não divulgar dados suficientes.
