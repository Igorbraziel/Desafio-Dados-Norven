# Desafio - Estágio Norven em Análise de Dados

Você é um analista de dados e recebe uma demanda para unir partes de uma mesma tabela em arquivos de formatos diferentes, transformar os dados e gerar um gráfico para análise dos resultados, além de uma planilha excel que enviará para outros analistas.

Os dados representam o registro diário de potência média (média calculada ao longo de 24 horas) de um cliente identificado pelo seu CPF ou CNPJ.

    Utilize um Jupyter Notebook ou Google Colab para registrar o código do desafio (Python 3.10 ou maior), mostrando e comentando os resultados obtidos.

---
## Primeira Etapa - Tratamento dos Dados
Abra, em python no notebook, as 6 tabelas tabulares na pasta [tabelas/](tabelas/), unifique-as em um mesmo dataframe e realize os tratamentos e limpeza das 5 colunas:

- **Coluna CPF/CNPJ:** Trate os valores para o mesmo padrão de CPF ou CNPJ. Caso o valor seja nulo ou esteja sem capacidade de ser transformado para um CPF ou CNPJ válido, descarte a linha.

- **Coluna UF:** Trate os valores para o mesmo padrão de nome. Caso o valor seja nulo ou sem capacidade de compreender qual UF/Estado está se referindo, descarte a linha.

- **Potência Média (kW):** Trate os valores para `float`. Os dados estão em kW. Caso o valor seja nulo ou esteja sem capacidade de ser transformado em float, descarte a linha.

- **Data do Dia:** Trate as datas para o mesmo formato de dia. Caso o valor seja nulo ou esteja sem capacidade de ser transformado em uma data válida, descarte a linha.

- **Classe:** Trate as classes para o mesmo formato. Caso o valor seja nulo ou esteja sem capacidade de ser transformado em uma das 8 classes, descarte a linha.

Uma pessoa física/jurídica só pode ter um registro por dia, então remova os valores duplicados.

Após essas tratativas, mostre, no notebook, como ficou o dataframe.

---
## Segunda Etapa - Transformação dos Dados
Utilize o dataframe da primeira etapa para gerar uma nova coluna chamada `CUSTO` que é calculado utilizando a tabela de kWh/dia conforme a classe.

| Classe | Cálculo           |
| ------ | ----------------- |
| A1     | 1kWh/dia = R$ 0.7 |
| A2     | 1kWh/dia = R$ 0.7 |
| B1     | 1kWh/dia = R$ 0.6 |
| B2     | 1kWh/dia = R$ 0.3 |
| C1     | Potência Média > 50kW,  1kWh/dia = R$ 1.5, caso contário 1kWh/dia = R$ 0.5 |
| C2     | Potência Média > 50kW,  1kWh/dia = R$ 1.5, caso contário 1kWh/dia = R$ 0.5 |
| D1     | 1kWh/dia = R$ 1.0 |
| D2     | 1kWh/dia = R$ 1.0 |

**Obs:** Lembre-se o Cálculo é feito utilizando kWh/dia e não kW. A Potência Média (kW) é a média da potência durante 24 horas, enquanto a kWh/dia é essa energia consumida durante o dia.

## Terceira Etapa - Resultados
Espera-setrês resultados, uma análise gráfica, uma planilha excel gerada por código e a resposta de algumas perguntas.

### Gráfico
Plote no notebook um Gráfico de Linhas Múltiplas (uma para cada UF) como Série Temporal da Soma dos Custos Mensais, como mostrado na imagem exemplo.

![alt text](image.png)

### Planilha Excel
Faça o código python que gere um arquivo excel contendo tabelas da somatória dos custo anual que cada CPF/CNPJ teve. Ou seja, uma coluna com valores únicos de CPF/CNPJ e outra com a soma anual dos custos que essa pessoa física/jurídica teve. Na planilha excel, separe em 5 abas, cada uma contendo apenas os registros de um ano. Ex: Aba 1 é de apenas 2020, Aba 2 é 2021, ...

**Obs:** Se quiser, pode tentar, somente pro código python, melhorar a visibilidade e estética da planilha.

### Perguntas
Responda, no próprio notebook, as seguintes perguntas:

    1. Qual UF/Estado possui a maior média de custo para a classe agrupada A (A1 e A2)?

    2. Qual UF/Estado possui a maior média de custo para a classe agrupada B (B1 e B2)?

    3. Qual UF/Estado possui a maior média de custo para a classe agrupada C (C1 e C2)?

    4. Qual UF/Estado possui a maior média de custo para a classe agrupada D (D1 e D2)?