# Banco API - Testes de Performance  

## 📌 Introdução  
Este repositório contém um conjunto de testes de performance desenvolvidos com **JavaScript** utilizando o **K6**.  
O objetivo é avaliar o desempenho e a resiliência da [API Banco](https://github.com/juliodelimas/banco-api), validando aspectos como **tempo de resposta**, **taxa de erros** e **capacidade de carga**.  

---

## ⚙️ Tecnologias Utilizadas  
- [K6](https://k6.io/) – Ferramenta para execução de testes de carga e performance.  
- JavaScript (ES6) – Linguagem utilizada para a definição dos cenários de teste.  

---

## 📂 Estrutura do Repositório  
```
banco-api-performance/
|-- fixtures/         # Dados de entrada
|-- helpers/          # Funções utilitárias para interação com a API
|-- tests/            # Casos de teste
│── utils/            # Funções auxiliares e configurações reutilizáveis
|-- config/           # Arquivos de Configuração
│── thresholds/       # Definições de limites de performance (SLAs/SLIs)
│── package.json      # Dependências e metadados do projeto
│── README.md         # Documentação do projeto
```

---

## 🎯 Objetivo de Cada Grupo de Arquivos  
- **fixtures/** → Dados de entrada
- **helpers/** → Funções utilitárias para interação com a API
- **tests/** → Casos de teste organizados por módulo da API
- **utils/** → Funções auxiliares e configurações reutilizáveis
- **config/** → Arquivos de Configuração
- **thresholds/** → Define métricas de performance mínimas aceitáveis (tempo de resposta, taxa de sucesso, etc.).  

---

## 🛠️ Instalação do Projeto  
Antes de rodar os testes, certifique-se de ter o [K6 instalado](https://grafana.com/docs/k6/latest/set-up/install-k6/).  

Clone este repositório:  
```bash
git clone https://github.com/AndyTex2003/banco-api-performance.git
cd banco-api-performance
```

---

## 🚀 Execução dos Testes  

### 1. Definindo a variável de ambiente da API  
Todos os testes utilizam a variável `BASE_URL`, que deve ser configurada antes da execução:  
```bash
export BASE_URL=http://localhost:3000
```
*(ou o endereço da API em produção/homologação)*  

No Windows (PowerShell):  
```powershell
$env:BASE_URL="http://localhost:3000"
```

### 2. Executando um teste simples  
```bash
k6 run test/login.test.js
```

### 3. Acompanhando relatórios em tempo real  
O K6 possui um dashboard web integrado que pode ser habilitado via variáveis de ambiente:  
```bash
BASE_URL=http://localhost:3000 K6_WEB_DASHBOARD=true K6_WEB_DASHBOARD_EXPORT=html-report.html k6 run scripts/<nome-do-teste>.js
```

- `K6_WEB_DASHBOARD=true` → abre um dashboard web em tempo real.  
- `K6_WEB_DASHBOARD_EXPORT=html-report.html` → exporta o relatório em HTML após a execução.  

---

🔗 **Repositório:** [banco-api-performance](https://github.com/AndyTex2003/banco-api-performance)  
