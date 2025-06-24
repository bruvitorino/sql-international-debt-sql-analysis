# 📊 Exame Prático – Analyze International Debt Statistics

Este repositório contém a solução do exame prático proposto pela [DataCamp](https://www.datacamp.com/) para análise de dados de dívida internacional, utilizando SQL dentro do ambiente Python (Google Colab).

---

## 🌍 Sobre o Conjunto de Dados

O conjunto de dados utilizado contém estatísticas financeiras internacionais de diversos países, incluindo valores de dívida, indicadores econômicos e códigos específicos fornecidos por instituições financeiras globais.

As informações foram extraídas de um arquivo `.csv` fornecido pela DataCamp, simulando uma base de dados relacional.

---

## 🎯 Objetivo da Análise

O desafio consiste em responder a três perguntas fundamentais utilizando **consultas SQL**:

1. Quantos países distintos estão representados no conjunto de dados?
2. Qual país possui o **maior valor total de dívida**?
3. Qual país possui o **menor valor de amortizações principais** (indicador `DT.AMT.DLXF.CD`)?

---

## 📁 Arquivo de Dados

- `international_debt.csv`: Contém dados sobre indicadores econômicos e financeiros por país.

---

## ✅ Tarefas Realizadas

### 1. Query – Total de Países Distintos

Consulta para contar o número de países únicos na base de dados:

```sql
SELECT COUNT(DISTINCT country_name) AS total_distinct_countries
FROM international_debt;

2. Query – País com Maior Dívida

Consulta para identificar o país com o maior valor de dívida acumulada:

SELECT country_name, SUM(debt) AS total_debt
FROM international_debt
GROUP BY country_name
ORDER BY total_debt DESC
LIMIT 1;

3. Query – Menor Amortização de Principal

Consulta para identificar o país com o menor valor registrado de amortização do principal da dívida (indicador DT.AMT.DLXF.CD):

SELECT country_name,
	   indicator_name,
	   MIN(debt) AS lowest_repayment
FROM international_debt
WHERE indicator_code = 'DT.AMT.DLXF.CD'
GROUP BY country_name, indicator_name
ORDER BY lowest_repayment ASC
LIMIT 1;

```
--- 

## 🛠️ Ferramentas Utilizadas

Python 3

SQLite (via sqlite3)

Pandas

Google Colab / Jupyter Notebook

---

## ▶️ Como Executar

Faça upload do arquivo international_debt.csv no Colab.

Execute o notebook international_debt_analysis.ipynb.

Acompanhe a execução das consultas SQL dentro do ambiente Python.

Visualize os resultados utilizando display() e formatações com pandas.

---

## 📂 Estrutura do Projeto

   -international-debt-analysis

   -README.md

   -international_debt_analysis.ipynb

   -international_debt.csv

## 📌 Observações

Este projeto foi desenvolvido com fins educacionais, como parte de um exame prático de análise de dados com SQL e Python.