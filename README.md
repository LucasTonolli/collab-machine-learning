# 🛡️ Análise e Classificação de Ameaças Cibernéticas Globais

Este projeto consiste em um notebook de Ciência de Dados que analisa um dataset de ataques cibernéticos (2015-2024). O objetivo principal é **criar um modelo preditivo** capaz de classificar o nível de impacto de um ataque com base em suas características técnicas e geográficas.

🔗 **Link do Dataset Original:** [Global Cybersecurity Threats (2015-2024)](https://www.kaggle.com/datasets/atharvasoundankar/global-cybersecurity-threats-2015-2024)

## 🎯 Objetivo do Projeto

Transformar dados brutos de perdas financeiras e usuários afetados em uma métrica de **Nível de Impacto** (Engenharia de Atributos via Clusterização) e, em seguida, treinar algoritmos de Machine Learning para prever esse impacto.

## 🔑 Configuração Obrigatória (Segredos do Kaggle)

Para executar este notebook, o download do dataset é feito automaticamente via API do Kaggle. **É necessário configurar as credenciais de acesso antes de rodar o código.**

### Passo a Passo no Google Colab:

1.  Acesse sua conta no [Kaggle](https://www.kaggle.com/).
2.  Vá em **Settings** -> seção **API** -> Clique em **Create New Token**. Um arquivo `kaggle.json` será baixado.
3.  Abra este arquivo e copie o `username` e a `key`.
4.  No Google Colab, clique no ícone de **Chave (Segredos)** na barra lateral esquerda (Secrets).
5.  Adicione dois novos segredos com os seguintes nomes exatos:
    * `kaggle_username`: (Insira seu usuário do Kaggle)
    * `kaggle_key`: (Insira sua chave API)
6.  Ative a opção "Notebook access" (Acesso ao notebook) para ambos os segredos.

> ⚠️ **Nota:** Sem essas credenciais configuradas nos segredos do Colab, a etapa de download do dataset falhará.

## 🛠️ Etapas do Projeto

O notebook está estruturado nas seguintes seções:

1.  **Setup e Carga de Dados:** Configuração do ambiente e download via API do Kaggle.
2.  **Análise Exploratória (EDA):** Verificação de distribuição, valores nulos e desbalanceamento.
3.  **Engenharia de Atributos (Criação do Target):**
    * Uso do algoritmo **K-Means** para agrupar ataques baseados em *Perda Financeira* e *Usuários Afetados*.
    * Definição das classes: **Impacto Médio**, **Impacto Alto** e **Impacto Crítico**.
4.  **Pré-Processamento:** Limpeza de dados e transformação de variáveis categóricas em numéricas (*Label Encoding*).
5.  **Modelagem Comparativa:** Treinamento e avaliação de três algoritmos:
    * Decision Tree (Árvore de Decisão)
    * Random Forest
    * Regressão Logística
6.  **Avaliação e Visualização:** Escolha do melhor modelo (Decision Tree) e plotagem das regras de decisão.

## 📊 Principais Resultados

* **Melhor Modelo:** A **Árvore de Decisão** apresentou o melhor equilíbrio entre performance (F1-Score) e custo computacional.
* **Clusterização:** Identificou-se que a maioria dos ataques no dataset cai na categoria de "Impacto Crítico" (Alta perda financeira + Alto número de usuários).
* **Insights:** O modelo teve facilidade em identificar ataques críticos, mas dificuldades em distinguir as classes minoritárias devido ao desbalanceamento natural dos dados.

---
*Desenvolvido para fins de estudo*