# 🔍 Audit Copilot Base

> Web3 development environment — Smart Contract analysis powered by AI, built with Scaffold-ETH 2, thirdweb AI and BuildBear sandboxes.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Built with Scaffold-ETH 2](https://img.shields.io/badge/Built%20with-Scaffold--ETH%202-blue)](https://scaffoldeth.io)
[![Powered by thirdweb AI](https://img.shields.io/badge/Powered%20by-thirdweb%20AI-purple)](https://thirdweb.com/ai)
[![Network: BuildBear](https://img.shields.io/badge/Sandbox-BuildBear-green)](https://buildbear.io)

---

## 🧠 O que é este projeto

**Audit Copilot Base** é a fundação de um Smart Contract Audit Copilot — uma ferramenta que analisa contratos Solidity com IA e entrega relatórios estruturados de vulnerabilidades em linguagem acessível.

Este repositório cobre a **Fase 1**: configuração do ambiente de desenvolvimento Web3, deploy de contratos em sandbox privado (BuildBear), e integração inicial com thirdweb AI para leitura de dados on-chain.

---

## 🗺️ Roadmap do Projeto

```
Fase 1 — Ambiente & Base (este repo)     ✅ em andamento
  └─ Scaffold-ETH 2 + Hardhat
  └─ BuildBear sandbox (fork testnet)
  └─ thirdweb AI — exploração inicial

Fase 2 — Audit Engine                    🔜 próxima
  └─ Pipeline: upload .sol → parse → LLM → relatório
  └─ Análise por severity (Critical / High / Medium / Low)
  └─ ChainGPT para geração e análise de Solidity

Fase 3 — Interface & Portfólio           🔜 em breve
  └─ Frontend Next.js com Wagmi
  └─ Export PDF do relatório
  └─ Deploy em produção
```

---

## 🛠️ Stack

| Camada | Ferramenta | Função |
|--------|-----------|--------|
| Smart Contracts | Solidity + Hardhat | Escrita e compilação de contratos |
| Dev Environment | Scaffold-ETH 2 | Boilerplate, debug UI, hooks Web3 |
| Sandbox | BuildBear | Fork de testnet, faucet ilimitado, explorer |
| AI On-chain | thirdweb AI (Nebula) | Leitura e análise de dados on-chain via IA |
| Frontend | Next.js + Wagmi | Interface e conexão de wallet |
| Linguagem | TypeScript | Type safety em todo o projeto |

---

## 🚀 Como rodar localmente

### Pré-requisitos

- Node.js >= 18
- Yarn >= 2.0.0

```bash
# Instalar Yarn se necessário
npm install -g yarn
```

### Instalação

```bash
# Clonar o repositório
git clone https://github.com/catitodev/audit-copilot-base.git
cd audit-copilot-base

# Instalar dependências
yarn install
```

### Rodar ambiente local

```bash
# Terminal 1 — sobe a blockchain local
yarn chain

# Terminal 2 — deploya os contratos
yarn deploy

# Terminal 3 — sobe o frontend
yarn start
```

Acesse `http://localhost:3000` para ver o ambiente rodando.

---

## 🧪 BuildBear — Sandbox em Testnet Real

Este projeto usa [BuildBear](https://buildbear.io) para criar um fork privado de testnet com:

- Faucet ilimitado (sem pedir tokens em faucets públicos)
- Block explorer próprio
- Estado persistente entre sessões
- Compatível com MetaMask e Wagmi

Para configurar seu próprio sandbox:

1. Crie conta em [buildbear.io](https://buildbear.io)
2. Crie um novo sandbox (fork da Base Sepolia ou Ethereum Sepolia)
3. Copie a RPC URL gerada
4. Atualize `packages/hardhat/hardhat.config.ts` com a RPC do seu sandbox

---

## 🤖 thirdweb AI — Exploração Inicial

Este projeto explora o [thirdweb AI (Nebula)](https://thirdweb.com/ai) para:

- Consultar dados on-chain de contratos deployados
- Analisar histórico de transações
- Base para o Audit Engine da Fase 2

Para testar sem código: [playground.thirdweb.com/ai/chat](https://playground.thirdweb.com/ai/chat)

---

## 📁 Estrutura do Projeto

```
audit-copilot-base/
├── packages/
│   ├── hardhat/          # Contratos Solidity + scripts de deploy
│   │   ├── contracts/    # Smart contracts
│   │   ├── deploy/       # Scripts de deploy
│   │   └── test/         # Testes dos contratos
│   └── nextjs/           # Frontend Next.js
│       ├── app/          # App Router pages
│       ├── components/   # Componentes React
│       └── hooks/        # Custom hooks Wagmi
├── .env.example          # Variáveis de ambiente necessárias
└── README.md
```

---

## 🔐 Variáveis de Ambiente

Crie um arquivo `.env.local` em `packages/nextjs/`:

```bash
# thirdweb
NEXT_PUBLIC_THIRDWEB_CLIENT_ID=sua_client_id

# BuildBear (opcional — para sandbox customizado)
NEXT_PUBLIC_BUILDBEAR_RPC=sua_rpc_url
```

> ⚠️ Nunca commite chaves privadas ou secrets. Use sempre `.env.local` (já no `.gitignore`).

---

## 🧩 Projetos desta Série

Este repositório faz parte de uma série de projetos Web3 + AI:

| # | Projeto | Descrição | Status |
|---|---------|-----------|--------|
| 1 | **audit-copilot-base** | Ambiente dev + exploração das ferramentas | ✅ Ativo |
| 2 | audit-copilot-engine | Pipeline de análise de contratos com IA | 🔜 Em breve |
| 3 | defi-protocol-dashboard | Dashboard de dados DeFi com Wagmi + DeFiLlama | 🔜 Em breve |

---

## 📚 Recursos e Documentação

- [Scaffold-ETH 2 Docs](https://docs.scaffoldeth.io)
- [thirdweb AI Docs](https://portal.thirdweb.com/ai/chat)
- [BuildBear Docs](https://docs.buildbear.io)
- [Wagmi Docs](https://wagmi.sh)
- [Hardhat Docs](https://hardhat.org/docs)

---

## 🤝 Contribuições

Contribuições, issues e sugestões são bem-vindas. Sinta-se livre para abrir uma issue ou PR.

---

## 📄 Licença

MIT © [catitodev](https://github.com/catitodev)
