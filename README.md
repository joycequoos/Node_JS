# Node.js API — DevHouse

[← Voltar](https://github.com/JosiTubaroski/DataScience/blob/main/README.md)

API REST desenvolvida em Node.js, utilizando Express para o servidor HTTP e MongoDB (via Mongoose) como banco de dados. O projeto expõe rotas de autenticação (sessões) e de cadastro de imóveis, incluindo upload de imagem de capa.

## Sobre o Projeto

Esta API serve como back-end para uma aplicação de listagem de imóveis (**DevHouse**), permitindo:

- **Autenticação de sessão** — rota para login/autenticação de usuários.
- **Cadastro de imóveis** — rota para criar um novo imóvel, com upload de uma imagem de thumbnail (miniatura).

## Tecnologias Utilizadas

| Tecnologia | Função no Projeto |
|---|---|
| **Node.js** | Ambiente de execução JavaScript no servidor. |
| **Express** | Framework para criação do servidor HTTP e das rotas da API. |
| **Mongoose** | Biblioteca para modelagem de dados e conexão com o MongoDB. |
| **Multer** | Middleware para upload de arquivos (imagens de imóveis). |

## Estrutura de Arquivos

| Arquivo | Descrição |
|---|---|
| [server.js](https://github.com/joycequoos/Node_JS/blob/main/server.js) | Ponto de entrada da aplicação — inicia o servidor na porta `3333`. |
| [app.js](https://github.com/joycequoos/Node_JS/blob/main/app.js) | Configuração principal da aplicação: conexão com o MongoDB, middlewares e carregamento das rotas. |
| [routes.js](https://github.com/joycequoos/Node_JS/blob/main/routes.js) | Definição das rotas da API e seus respectivos controllers. |

## Rotas da API

| Método | Rota | Descrição |
|---|---|---|
| `POST` | `/sessions` | Autentica um usuário (login). |
| `POST` | `/houses` | Cadastra um novo imóvel, recebendo a imagem de thumbnail via upload (`multipart/form-data`). |

## Como Executar

```bash
# instalar as dependências
npm install

# iniciar o servidor
node server.js
```

O servidor ficará disponível em `http://localhost:3333`.

## Observação sobre Segurança

O arquivo `app.js` atualmente contém a string de conexão do MongoDB (usuário e senha) diretamente no código. Para projetos em produção, o recomendado é mover essas credenciais para variáveis de ambiente (por exemplo, usando um arquivo `.env` com a biblioteca `dotenv`), evitando expor dados sensíveis no repositório.
