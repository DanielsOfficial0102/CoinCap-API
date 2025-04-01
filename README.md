# 📊 Projeto de Análise de Cotação de Criptomoedas

## 📌 Introdução

Este projeto tem como objetivo coletar, processar e analisar dados de cotação de criptomoedas utilizando MySQL para armazenamento e Power BI para visualização dos insights.

## 🏗️ Arquitetura

1. **Fonte de Dados**: API CoinCap (dados de criptomoedas em tempo real).
2. **Armazenamento**: MySQL hospedado no Google Cloud Platform.
3. **Processamento**: Python (coleta e inserção de dados).
4. **Visualização**: Power BI (dashboard interativo).

## 📂 Estrutura do Banco de Dados

O banco de dados foi estruturado em **tabelas normalizadas** para otimizar a análise:

### **1. Tabela RAW (crypto\_prices)**

Armazena os dados brutos coletados da API.

| Coluna           | Tipo                    | Descrição                    |
| ---------------- | ----------------------- | ---------------------------- |
| id               | VARCHAR(50) PRIMARY KEY | Identificador da criptomoeda |
| symbol           | VARCHAR(10)             | Símbolo (ex: BTC)            |
| name             | VARCHAR(100)            | Nome da criptomoeda          |
| price\_usd       | DECIMAL(18,8)           | Preço em USD                 |
| market\_cap\_usd | DECIMAL(18,2)           | Capitalização de mercado     |
| supply           | DECIMAL(38,10)          | Quantidade em circulação     |
| timestamp        | TIMESTAMP               | Momento da coleta            |

### **2. Dimensões**

- **dim\_moeda**: Contém os nomes das criptomoedas sem repetição.
- **dim\_calendario**: Tabela com datas e informações temporais.

### **3. Tabela Fato**

- **fato\_cotacao**: Contém os valores históricos de preços das criptomoedas.

## 🔄 Pipeline de Dados

1. Coleta de dados via API CoinCap.
2. Inserção na tabela RAW `crypto_prices`.
3. Atualização das tabelas dimensionais `dim_moeda` e `dim_calendario`.
4. Inserção na tabela fato `fato_cotacao`.
5. Integração com Power BI para análise.

## 📊 Dashboard (Power BI)

O dashboard foi construído para visualizar:

- **Evolução do preço** das criptomoedas.
- **Distribuição da capitalização de mercado**.
- **Variação histórica** dos valores.

## 🚀 Como Reproduzir o Projeto

1. Clone o repositório:
   
2. Configure o banco de dados MySQL no Google Cloud Platform.
3. Execute o script Python para coleta e inserção de dados.
4. Conecte o Power BI ao banco MySQL.

## 🛠 Tecnologias Utilizadas

- **Python** (requests, pandas, SQLAlchemy)
- **MySQL** (armazenamento de dados)
- **Google Cloud Platform** (hospedagem do banco)
- **Power BI** (dashboard interativo)

---

Qualquer dúvida ou sugestão, entre em contato! 🚀

