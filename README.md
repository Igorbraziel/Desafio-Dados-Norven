# Desafio - Estágio Norven em Análise de Dados

Este repositório contém a solução do desafio proposto pelo **Estágio Norven em Análise de Dados**. O objetivo do desafio foi tratar, transformar e analisar dados de potência média de clientes, gerando visualizações e planilhas para suporte à decisão.

---

## 📝 Descrição do Desafio

O desafio foi dividido em três etapas principais:

### 1️⃣ Tratamento dos Dados
- Leitura e unificação de 6 tabelas em um único DataFrame.
- Limpeza das colunas:
  - **CPF/CNPJ:** padronização e exclusão de registros inválidos.
  - **UF:** padronização de estados brasileiros.
  - **Potência Média (kW):** conversão para float.
  - **Data do Dia:** padronização de datas.
  - **Classe:** padronização em 8 classes possíveis.
- Remoção de duplicatas, garantindo um registro por pessoa física/jurídica por dia.
- Visualização do DataFrame final após tratamento.

### 2️⃣ Transformação dos Dados
- Criação da coluna `CUSTO`, calculada com base na **potência média diária (kWh/dia)** e na classe do cliente.
- Tabela de referência de cálculo por classe:

| Classe | Cálculo |
|--------|---------|
| A1, A2 | 1 kWh/dia = R$ 0.7 |
| B1     | 1 kWh/dia = R$ 0.6 |
| B2     | 1 kWh/dia = R$ 0.3 |
| C1, C2 | >50kW: 1 kWh/dia = R$ 1.5; ≤50kW: 1 kWh/dia = R$ 0.5 |
| D1, D2 | 1 kWh/dia = R$ 1.0 |

---

### 3️⃣ Resultados
- **Gráfico de Linhas Múltiplas:** Série temporal da soma dos custos mensais por UF.
- **Planilha Excel:** 
  - Contendo o custo anual de cada CPF/CNPJ.
  - Separada em **5 abas**, uma para cada ano.
  - Tabelas organizadas para melhor visualização.

- **Análises:**
  1. UF com maior média de custo para classes **A1 e A2**
  2. UF com maior média de custo para classes **B1 e B2**
  3. UF com maior média de custo para classes **C1 e C2**
  4. UF com maior média de custo para classes **D1 e D2**

---

## 🛠 Tecnologias Utilizadas
- Python 3.10+
- Pandas
- NumPy
- Matplotlib
- OpenPyXL / XlsxWriter (para Excel)
- Google Colab

---
