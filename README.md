# BotZelvon Geoapify V5

## Integração NATIVA

A categoria **Açaiterias / sorveterias / sobremesas** agora usa o projeto:

https://nativa-seven.vercel.app/

O BotZelvon cria automaticamente uma URL personalizada com:

- nome do negócio
- cidade
- endereço
- telefone/WhatsApp quando disponível
- Instagram quando disponível
- avaliações ilustrativas ocultas

Exemplo:

`https://nativa-seven.vercel.app/?nome=Nome%20do%20Lead&cidade=Tabo%C3%A3o%20da%20Serra%2C%20SP&whatsapp=5511...&avaliacoes=0`

## Fluxo

1. Buscar negócios
2. Clicar em **Ver proposta**
3. Conferir a versão personalizada
4. Clicar em **Preparar mensagem**
5. Revisar
6. Abrir WhatsApp
7. O envio permanece manual

A variável `GEOAPIFY_API_KEY` continua igual no Vercel.
