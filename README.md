## 📘 CRISP-DM: Data Preparation na Prática  
### 🔧 Preparação de Dados (Data Preparation) no Processo CRISP-DM  

A preparação de dados é uma das etapas mais cruciais no ciclo de vida de um projeto de Data Science, e no contexto do processo CRISP-DM (Cross Industry Standard Process for Data Mining), ela é fundamental para garantir que os dados estejam prontos para serem analisados e modelados. Esta fase envolve diversas atividades, incluindo a **limpeza**, **transformação**, **integração** e **formatação** dos dados brutos, de modo que possam ser utilizados de forma eficaz nas fases subsequentes do projeto.

---

### 📥 Imports e Carregamento dos Dados Brutos  
O primeiro passo na preparação de dados é carregar os dados brutos (raw dataset) em um ambiente de trabalho, geralmente utilizando bibliotecas como o `pandas` no Python.  
Um exemplo disso é a importação de um arquivo CSV contendo dados de campanhas de financiamento coletivo.  
A pré-visualização dos dados com `df.head()` nos permite entender a estrutura e as variáveis presentes.

---

### 🧩 Seleção de Dados Relevantes  
Após carregar o dataset, é importante selecionar as colunas que são relevantes para a análise.  
Neste caso, foram removidas colunas que não acrescentariam valor ao modelo, como `Unnamed: 0`, `name`, `category`, entre outras.  
Esse processo de seleção é essencial para reduzir a dimensionalidade dos dados e focar apenas nas informações que realmente importam.

---

### 🧹 Limpeza de Dados  
A limpeza de dados envolve a remoção de valores inválidos ou inconsistentes.  
Por exemplo:
- A coluna `usd_goal_real` tinha o prefixo `"USD "`, que foi removido para facilitar a conversão para um tipo de dado numérico.
- A coluna `launched`, que continha informações de data e hora, foi transformada para manter apenas a data, removendo a hora com o uso de expressões regulares.

---

### 🔄 Conversão de Tipos de Dados  
Garantir que cada coluna tenha o tipo de dado correto é vital.  
Exemplos:
- Colunas como `usd_goal_real`, inicialmente do tipo `object`, foram convertidas para `int64`.
- As colunas de datas (`deadline` e `launched`) foram convertidas para o formato `datetime64[ns]` para permitir operações temporais precisas.

---

### 🧱 Construção de Novas Variáveis  
A criação de novas colunas a partir de dados existentes pode fornecer insights adicionais.  
Por exemplo:
- A coluna `time_range` foi criada para representar o número de dias entre a data de lançamento e o prazo final de uma campanha.

---

### 🔗 Integração de Dados  
No processo de preparação de dados, muitas vezes é necessário integrar diferentes datasets.  
Neste exemplo, foram feitas várias junções (`merge`) de tabelas adicionais (`df_campaign` e `df_invested`), que continham informações complementares sobre as campanhas.  
Técnicas como `OneHotEncoding` foram usadas para transformar variáveis categóricas em numéricas.  
Também foram realizadas agregações (`groupby + agg`) para consolidar informações, como a idade média dos investidores e a localização deles.

---

### 🗃️ Formatação dos Dados  
A formatação é uma etapa contínua que ocorre ao longo de todo o processo de preparação de dados.  
Envolve:
- Transformar e padronizar os tipos de dados  
- Renomear colunas  
- Reordenar registros  
Tudo isso para garantir a **consistência** e a **qualidade** do dataset final.

---

### ✅ Conclusão  
O dataset bruto inicial foi transformado em um dataset **limpo** e **estruturado**, pronto para ser usado nas próximas fases do processo CRISP-DM, como a modelagem e a avaliação.  
Esta preparação cuidadosa dos dados é **crucial para o sucesso** de qualquer projeto de Data Science, pois garante que os modelos sejam construídos com dados de alta qualidade, minimizando erros e maximizando a precisão das previsões.
