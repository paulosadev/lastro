# Lastro

IA que revisa o post do creator antes da publicação: compara cada promessa com a ficha do produto e com as regras do Conar, da Anvisa e do CDC, e devolve uma versão que vende sem prometer o que o produto não entrega.

Protótipo do Desafio de Inovação YouShop 2027, por Paulo Levy.

## Como funciona

- `index.html`: a página (tela do creator e painel de Operações com dados de exemplo).
- `api/analisar.js`: função serverless da Vercel que chama a Groq (modelo `openai/gpt-oss-120b`). A chave fica só no servidor.
- As fichas de produto ficam no servidor, para ninguém trocar a régua pelo navegador.
- Limite de 8 análises por minuto por IP e textos de até 2.000 caracteres.

## Publicar na Vercel

1. Crie uma chave em https://console.groq.com/keys
2. Suba esta pasta para um repositório no GitHub.
3. Na Vercel: Add New › Project › importe o repositório. Framework: Other. Não precisa de build.
4. Em Settings › Environment Variables, crie `GROQ_API_KEY` com a sua chave.
5. Faça um novo deploy e teste em uma janela anônima.

Opcional: `GROQ_MODEL` troca o modelo usado.
