# DT Money

Aplicacao web para controle financeiro pessoal com cadastro, busca e listagem de transacoes, alem de resumo de entradas, saidas e total.

## Preview

Principais funcionalidades:

- Cadastro de novas transacoes (entrada e saida)
- Busca de transacoes por texto
- Tabela de transacoes com data, categoria e valor formatado
- Resumo financeiro com totalizadores

## Tecnologias utilizadas

- React 18
- TypeScript
- Vite
- Styled Components
- React Hook Form
- Zod
- Axios
- Radix UI (Dialog e Radio Group)
- json-server (mock de API REST)
- use-context-selector

## Requisitos

- Node.js 18+
- npm 9+

## Como executar o projeto

1. Instale as dependencias:

```bash
npm install
```

2. Em um terminal, inicie a API mock local:

```bash
npm run dev:server
```

3. Em outro terminal, inicie a aplicacao web:

```bash
npm run dev
```

4. Acesse no navegador:

- Frontend: http://localhost:5173
- API mock: http://localhost:3333

## Scripts disponiveis

- `npm run dev`: inicia o frontend com Vite
- `npm run dev:server`: inicia o json-server na porta 3333
- `npm run build`: gera build de producao
- `npm run preview`: executa o preview da build
- `npm run lint`: executa o ESLint

## Estrutura de pastas

```text
src/
  components/              # Componentes reutilizaveis
  contexts/                # Estado global (transacoes)
  hooks/                   # Hooks customizados
  lib/                     # Configuracoes de bibliotecas (axios)
  pages/                   # Paginas da aplicacao
  styles/                  # Tema e estilos globais
  utils/                   # Funcoes utilitarias (formatadores)
```

## API local (json-server)

O projeto utiliza o arquivo `server.json` como banco de dados fake.

Endpoint principal:

- `GET /transactions`: lista transacoes
- `GET /transactions?q=texto`: filtra por busca textual
- `POST /transactions`: cria nova transacao

Exemplo de payload para criacao:

```json
{
  "description": "Freelance",
  "price": 1500,
  "category": "Trabalho",
  "type": "income"
}
```

## Observacoes

- A URL base da API esta definida em `src/lib/axios.ts` como `http://localhost:3333`.
- Para o funcionamento completo da aplicacao, frontend e json-server devem estar rodando ao mesmo tempo.
