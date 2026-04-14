# 🚢 Desafio Lighthouse — Análise de Dados End-to-End

Projeto desenvolvido como parte do **Desafio Técnico da Lighthouse**, com o objetivo de atuar como um profissional de dados completo — desde a ingestão e tratamento até modelagem analítica e sistemas inteligentes.

---

## 📌 Contexto

A **LH Nautical** é uma empresa líder no varejo de peças e acessórios para embarcações, com operação híbrida (loja física + e-commerce nacional).

Com o crescimento acelerado, surgiram desafios relacionados a:

- Qualidade dos dados  
- Organização das bases  
- Eficiência operacional  
- Tomada de decisão baseada em dados  

---

## 🎯 Objetivo do Projeto

Transformar dados brutos em **insights estratégicos e soluções analíticas**, passando por todo o ciclo de dados:

- Engenharia de Dados  
- Análise Exploratória (EDA)  
- Modelagem em SQL  
- Análise de Negócio  
- Machine Learning  
- Sistemas de Recomendação  

---

## 🧩 Etapas do Projeto

### 1. 📊 Análise Exploratória de Dados (EDA)

**Dataset:** `vendas_2023_2024.csv`

**Pontos positivos:**
- 9.895 registros sem valores nulos  
- Sem valores negativos ou zerados  
- Cobertura completa de 2 anos (2023–2024)  

**Pontos de atenção:**
- Forte presença de outliers (máx: R$ 2,2 milhões)  
- Alta assimetria nos dados de vendas  
- Inconsistência no formato de datas (YYYY-MM-DD vs DD-MM-YYYY)  

**Conclusão:**  
Os dados **não estavam prontos para análise direta**, exigindo tratamento prévio.

---

### 2. 🧱 Tratamento e Normalização de Produtos

**Arquivo:** `produtos_raw.csv`

- Padronização de colunas  
- Limpeza de dados inconsistentes  
- Conversão de tipos  
- Remoção de registros inválidos  

**Resultado:**
- 7 linhas removidas  
- Dataset estruturado e pronto para análise  

---

### 3. 💰 Estruturação de Custos de Importação

**Arquivo:** `custos_importacao.json`

- Normalização de dados aninhados  
- Transformação para formato tabular  

**Resultado:**
- Dados prontos para consultas em SQL  

---

### 4. 📉 Análise de Prejuízo (Dados Públicos + Câmbio)

**Objetivo:** identificar vendas com prejuízo real  

**Metodologia:**
- Integração com API do Banco Central (PTAX)  
- Uso do câmbio do dia (*forward fill* para datas sem cotação)  

**Fórmula:**
```sql
custo_brl = usd_price_unit * qtd * taxa_cambio
```

**Regra de prejuízo:**
```
Quando custo_brl > receita
```

Insights:

- Produtos com até 61,32% de prejuízo
- Identificação de falhas operacionais
---
### 5. 👥 Análise de Clientes

**Objetivo:** identificar clientes fiéis

**Critérios:**
- Alto ticket médio
- Compras recorrentes
- Diversidade de categorias

**Resultado:**
- Segmentação de clientes premium
- Base para estratégias de retenção
---
### 6. 📅 Dimensão de Calendário

**Problema:** Dias sem venda não estavam registrados → médias infladas

**Solução:**
- Criação de tabela calendário
- Uso de LEFT JOIN para incluir dias zerados

**Resultado:**
- Métricas mais realistas
- Correção de viés analítico
---
### 7. 📈 Previsão de Demanda

**Problema:** 
- Ruptura de estoque
- Excesso de produtos

**Solução:**
- Modelo preditivo de vendas

**Resultado:**
- Melhor planejamento de compras
- Redução de perdas
---
### 8. 🛒 Sistema de Recomendação

**Objetivo:**
- Criar sistema do tipo: "Quem comprou isso, também levou..."

**Caso analisado:**

**Produto:** 
- GPS Garmin Vortex Maré Drift

**Solução:** 
- Recomendação baseada em similaridade de compras

**Impacto:**
- Aumento de vendas cruzadas
- Melhor experiência do cliente
---
## 🛠️ Tecnologias Utilizadas
- Python (Pandas, Numpy, Scikit-learn)
- SQL (DuckDB)
- APIs externas (Banco Central - PTAX)
- Modelagem de dados
- Machine Learning
- Análise estatística
----
## 📁 Estrutura do Projeto
```bash
Desafio-Lighthouse/
│
├── datasets/
├── scripts/
├── README.md
└── requirements.txt
```
----
## 🚀 Principais Resultados
- Identificação de inconsistências críticas nos dados
- Estruturação completa para análise em SQL
- Descoberta de prejuízos ocultos
- Segmentação de clientes estratégicos
- Previsão de demanda
- Sistema de recomendação funcional
- Insights e resultados visuais: https://drive.google.com/file/d/1Aa2t5OWXn5w23H19-tvM-1r11wSkaqQN/view?usp=sharing
- ----
## 📊 Visão Final
```
"O futuro é data-driven."
```

- Este projeto demonstra a capacidade de transformar dados em decisões estratégicas, cobrindo todo o ciclo de dados — da engenharia à inteligência artificial.

-----
## 👩‍💻 Autora
```
Lívia Marques Rodrigues
```
Projeto desenvolvido como parte do desafio técnico da Lighthouse 🚀
