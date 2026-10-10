<p align="center"><img src="./public/cashflow1.png" alt="CashFlow+" width="320"></p>

# CashFlow+

Aplicativo web de **controle financeiro pessoal**: registre entradas e saídas, acompanhe o saldo em tempo real e filtre suas transações por nome, tipo e período.

API: [cash-flow-api](https://github.com/LucianoMachadoS/cash-flow-api)

![React](https://img.shields.io/badge/React_19-20232A?style=flat&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat&logo=vite&logoColor=white)
![Axios](https://img.shields.io/badge/Axios-5A29E4?style=flat&logo=axios&logoColor=white)


## ✨ Funcionalidades

- **Resumo** com saldo geral, total de créditos e total de débitos (cartão fica vermelho quando o saldo é negativo)
- **Nova transação** em um modal: título, valor, tipo, categoria, forma de pagamento (PIX, boleto, cartão…) e data
- **Editar** transações pelo mesmo modal
- **Tabela de transações** que se atualiza sozinha ao adicionar ou editar
- **Filtros** por nome, tipo e intervalo de datas com calendário
- Categorias e formas de pagamento exibidas em português

## 🧱 Arquitetura

```
src/
├── components/   # AddTransaction, Modal, SearchBar, Summary, SummaryCard, TableRow, calendários
├── contexts/     # TransactionContext e FilterContext (estado global com Context API)
├── constant/     # rótulos em português das categorias e formas de pagamento
├── lib/axios.ts  # cliente HTTP com a URL da API vinda do .env
└── pages/        # página de Transações
```

O estado das transações e do resumo fica em **Context API**: qualquer componente que altera dados chama `refreshTransactions` / `refreshSummary`, e a tela inteira se atualiza.

## 🚀 Como rodar

Suba primeiro a [API](https://github.com/LucianoMachadoS/cash-flow-api). Depois:

```bash
git clone https://github.com/LucianoMachadoS/cash-flow.git
cd cash-flow
npm install
```

Crie um `.env`:

```env
VITE_BASE_URL=http://localhost:3333/transactions
```

```bash
npm run dev
```

Abra `http://localhost:5173`.

## 📚 O que aprendi

React 19 com TypeScript e hooks, estado global com Context API, componentes reutilizáveis, consumo de API com Axios e variáveis de ambiente no Vite.

## 🗺️ Próximos passos

- [ ] Gráfico de gastos por categoria
- [ ] Paginação na tabela
- [ ] Usar `Intl.NumberFormat` também nos cartões de resumo (hoje só a tabela usa)
- [ ] Login de usuário
- [ ] Deploy na Vercel

---
Feito por [Luciano Machado](https://github.com/LucianoMachadoS) · [LinkedIn](https://www.linkedin.com/in/luciano-machado-9253a1265/)
