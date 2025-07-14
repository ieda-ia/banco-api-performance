# Testes de Performance com JavaScript e K6

## 🧾 Introdução

Este repositório contém testes de performance desenvolvidos com a ferramenta [K6](https://k6.io/) utilizando JavaScript. O objetivo é avaliar o desempenho de APIs, com foco inicial em endpoints do sistema "Banco API".

## 🛠 Tecnologias Utilizadas

- [K6](https://k6.io/) - Ferramenta de teste de carga e performance.
- JavaScript - Linguagem de scripting para os testes.
- Node.js - Ambiente de execução para JavaScript (em alguns scripts auxiliares).
- Git - Controle de versão.

## 📁 Estrutura do Repositório

```
banco-api-performance/
├── config/       # Arquivo de configuração de variáveis de ambiente
├── fixtures/     # Dados de entrada para os testes (ex: usuários, payloads)
│── helpers/      # Funções utilitárias reutilizáveis
├── tests/        # Casos de teste organizados por módulo da API
├── utils/        # Funções utilitárias reutilizáveis
└── README.md     # Este domcumento
```

## 📂 Objetivo de Cada Grupo de Arquivos

- **`config/`**: Arquivo de configuração de variáveis de ambiente.
- **`fixtures/`**: Dados de entrada para os testes (ex: usuários, payloads).
- **`helpers/`**: unções utilitárias reutilizáveis.
- **`tests/`**: Casos de teste organizados por módulo da API.
- **`utils/`**: unções utilitárias reutilizáveis.
- **`README.md`**: Este domcumento.

## ⚙️ Instalação

1. Clone o repositório:
   ```bash
   git clone https://github.com/ieda-ia/banco-api-performance.git
   cd banco-api-performance
   ```

2. Instale o [K6](https://k6.io/docs/getting-started/installation/).

## ▶️ Execução dos Testes

Antes de executar qualquer teste, defina a variável da URL a ser testada no arquivo `configLocal.json`:

```json
{
    "baseURL": "http://localhost:3000"
}
```
Essas variáveis serão usadas dinamicamente nos testes para montar as requisições.

### Executar um teste (exemplo):

```bash
k6 run tests/login.test.js
```
Certifique-se de passar a variável de ambiente `BASE_URL`, caso não esteja usando um `config.local.json` ou uma abordagem de carregamento automático: 

```bash
k6 run tests/login.test.js -e BASE_URL=http://localhost:3000
```

### Acompanhamento com Dashboard Web em Tempo Real e Exportação

Você pode acompanhar os testes em tempo real com o dashboard web do K6 e ainda exportar os resultados em HTML:

```bash
K6_WEB_DASHBOARD=true \ 
K6_WEB_DASHBOARD_EXPORT=html-report.html \
k6 run tests/login.js \
-e BASE_URL=http://localhost:3000
```

O relatório será salvo como `html-report.html` ao final da execução.

---

Repositório: [banco-api-performance](https://github.com/ieda-ia/banco-api-performance)
