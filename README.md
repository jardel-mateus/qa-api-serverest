# qa-api-serverest

[![api](https://github.com/jardel-mateus/qa-api-serverest/actions/workflows/api.yml/badge.svg)](https://github.com/jardel-mateus/qa-api-serverest/actions/workflows/api.yml)

Testes de API da [ServeRest](https://serverest.dev) com Postman e Newman.

Relatório da última execução: https://jardel-mateus.github.io/qa-api-serverest/

## Fluxo

A coleção roda em sequência e limpa o que cria:

1. **Usuários:** cadastro de admin (e-mail gerado na hora), e-mail repetido, e-mail inválido, campos obrigatórios e busca por id
2. **Login:** sucesso (guarda o token) e senha errada
3. **Produtos:** sem token (401), cadastro, nome repetido, busca, alteração, conferência da alteração, exclusão e busca depois de excluir
4. **Limpeza:** exclui o usuário criado

São 16 requisições e 34 asserções (status, mensagens, dados retornados e tempo de resposta).

## Rodando

Dá pra importar o `serverest.postman_collection.json` no Postman ou rodar pelo terminal:

```bash
npm ci
npm test
```

O relatório HTML fica em `relatorio/index.html`. No GitHub Actions roda a cada push e todo dia útil, e o relatório vai pro GitHub Pages.
