# Projeto-Integrador

````markdown
📊 Análise de Sentimentos em Avaliações de Marketplace

Projeto desenvolvido para a disciplina **PII 3**, com foco em **pré-processamento de dados**, **análise de sentimentos** e **avaliação de modelos**, utilizando avaliações de clientes de um marketplace.

🎯 Objetivo

Aplicar técnicas de tratamento de dados e análise de sentimentos para estimar a nota de uma avaliação (**1 a 5 estrelas**) utilizando apenas o texto do comentário do cliente.

O projeto compara diferentes abordagens de análise de sentimentos e avalia sua capacidade de representar a percepção real dos consumidores.

---

📂 Base de Dados

O projeto utiliza diferentes tabelas do marketplace, sendo a principal:

- `avaliacoes.csv`

Também são carregados:

- `clientes.csv`
- `pedidos.csv`
- `produtos.csv`
- `pagamentos.csv`
- `itens_pedidos.csv`

A análise concentra-se principalmente nas colunas:

| Coluna | Descrição |
|----------|------------|
| `review_comment_message` | Comentário do cliente |
| `review_score` | Nota atribuída (1 a 5) |
| `review_creation_date` | Data da avaliação |
| `review_answer_timestamp` | Data da resposta |

---

🔄 Fluxo do Projeto

```text
Etapa 1 → Tipagem de Dados
Etapa 2 → Tratamento de Dados
Etapa 3 → Análise de Sentimentos
Etapa 4 → Interpretação dos Resultados
Etapa 5 → Avaliação dos Modelos
````

---

# 🛠 Tecnologias Utilizadas

## Bibliotecas Principais

* Pandas
* NumPy
* Matplotlib
* Scikit-Learn
* NLTK
* VADER Sentiment
* TextBlob
* Transformers
* PySentimiento
* Torch

Instalação:

```bash
pip install pandas numpy matplotlib scikit-learn
pip install nltk vaderSentiment textblob
pip install transformers torch
pip install pysentimiento
```

---

# 📌 Etapa 1 – Tipagem de Dados

Nesta etapa são identificados e corrigidos os tipos das colunas.

### Ajustes realizados

* IDs convertidos para `string`
* Comentários convertidos para `string`
* Notas convertidas para `int`
* Datas convertidas para `datetime`

### Benefícios

✅ Menor consumo de memória

✅ Melhor compatibilidade com análises

✅ Preparação para Machine Learning

---

# 🧹 Etapa 2 – Tratamento dos Dados

Foram realizados diversos processos de limpeza:

### Tratamento de valores nulos

* Remoção de registros sem comentários
* Verificação de campos obrigatórios

### Remoção de duplicidades

* Identificação e exclusão de registros repetidos

### Padronização textual

* Conversão para minúsculas
* Remoção de caracteres especiais
* Limpeza de espaços extras

### Resultado

Uma base consistente e pronta para análise de sentimentos.

---

# 😊 Etapa 3 – Análise de Sentimentos

Foram comparadas três abordagens diferentes.

---

## 1️⃣ VADER

### Características

* Baseado em léxico
* Utiliza dicionário de palavras positivas e negativas
* Considera pontuação e intensificadores

### Métrica

Retorna um score de sentimento entre:

```text
-1 → Muito negativo
+1 → Muito positivo
```

---

## 2️⃣ TextBlob

### Características

* Análise baseada em polaridade
* Simples e rápida

### Métricas

* Polarity (-1 a +1)
* Subjectivity (0 a 1)

### Limitação

Foi originalmente desenvolvido para inglês, podendo apresentar menor desempenho em textos em português.

---

## 3️⃣ BERT para Português (PySentimiento)

### Características

* Baseado em BERTimbau
* Treinado especificamente para português brasileiro
* Compreende contexto, negações e expressões informais

### Classes previstas

* Positivo
* Neutro
* Negativo

### Vantagem

Apresenta maior capacidade de interpretação semântica em comparação aos métodos léxicos.

---

# 📈 Etapa 4 – Interpretação dos Resultados

Nesta fase são analisadas:

* Distribuições de sentimentos
* Relação entre sentimento e nota real
* Comparação entre modelos

São gerados gráficos para facilitar a interpretação dos resultados.

---

# 📊 Etapa 5 – Avaliação dos Modelos

Foram utilizadas métricas estatísticas para verificar a qualidade das previsões.

---

## Correlação de Pearson

Avalia a relação linear entre:

```text
Nota Real × Nota Predita
```

### Interpretação

| Valor       | Correlação  |
| ----------- | ----------- |
| 0.00 – 0.19 | Desprezível |
| 0.20 – 0.39 | Fraca       |
| 0.40 – 0.69 | Moderada    |
| 0.70 – 0.89 | Forte       |
| 0.90 – 1.00 | Muito forte |

---

## Correlação de Spearman

Mais adequada para este problema porque:

* As notas são ordinais
* Não exige normalidade dos dados
* É robusta para distribuições assimétricas

---

## Matriz de Confusão

Utilizada para comparar:

```text
Nota Real × Nota Predita
```

### Métricas calculadas

* Acurácia
* MAE (Mean Absolute Error)
* Distribuição dos erros

---

# 📋 Resultados Esperados

Ao final da execução do notebook é possível:

* Comparar diferentes técnicas de análise de sentimentos
* Avaliar a capacidade de prever notas a partir de comentários
* Identificar qual abordagem apresenta melhor desempenho para textos em português

---

# 🚀 Como Executar

1. Clone o repositório

```bash
git clone https://github.com/seu-usuario/analise-sentimentos-marketplace.git
```

2. Acesse a pasta

```bash
cd analise-sentimentos-marketplace
```

3. Instale as dependências

```bash
pip install -r requirements.txt
```

4. Execute o notebook

```bash
jupyter notebook
```

Abra:

```text
analise_sentimentos_final.ipynb
```

---

# 🎓 Contexto Acadêmico

Projeto desenvolvido como atividade da disciplina **PII 3**, aplicando conceitos de:

* Ciência de Dados
* Processamento de Linguagem Natural (PLN)
* Machine Learning
* Estatística Aplicada
* Análise de Sentimentos

---
# 👨‍🏫 Orientador

**Felipe Camargo**

# 👨‍💻 Autores

**Gustavo P. Suzart**
**Diogo Eduardo Barbosa**
**Davi Nakaharada**
**Gabriel Campos da Paixão**


Estudantes de Inteligência em Análise de Dados
SENAI Suíço-Brasileira

---
