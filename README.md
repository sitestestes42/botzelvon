# Radar de Negócios — Geoapify

Versão para Vercel com backend serverless. A chave da Geoapify fica no servidor e não aparece no HTML.

## Configuração

1. Crie um projeto no Geoapify MyProjects e gere uma API key.
2. No Vercel: **Project > Settings > Environment Variables**.
3. Crie a variável `GEOAPIFY_API_KEY` e cole a chave como valor.
4. Marque Production (e Preview/Development, se desejar).
5. Faça um novo deploy.
6. Abra `/api/health`: `configured: true` confirma que a variável existe.
7. Abra a página principal, escolha cidade/segmento e clique em **Buscar negócios**.

## Como funciona

- `api/search.js` usa a Geocoding API para localizar a cidade.
- Depois usa a Places API para listar estabelecimentos dentro da cidade.
- Para até 12 resultados, usa Place Details para buscar telefone e website quando disponíveis.
- O frontend monta a mensagem e abre o WhatsApp com o texto preenchido; o envio permanece manual.

## Estrutura

- `index.html` — painel
- `api/search.js` — Geoapify Geocoding + Places + Place Details
- `api/health.js` — verifica se a variável está configurada sem revelar a chave
- `privacy.html` e `terms.html` — páginas-base; revise antes de uso público

## Uso gratuito e atribuição

No plano gratuito, mantenha visíveis as atribuições Geoapify e OpenStreetMap presentes no rodapé. O painel limita cada busca a até 12 leads para reduzir consumo de créditos e tempo de execução.

## Segurança

Nunca coloque a chave no HTML ou em JavaScript executado no navegador. Se uma chave for exposta publicamente, gere outra no Geoapify e atualize a variável no Vercel.
