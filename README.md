# Sprint-3-ToothFairy: Sistema de Recomendação de Planos Odontológicos com Machine Learning

## Integrantes
*    Bruno Burian – RM 552863
*    Lucca Augusto Matteoni – RM 98146
*    Luccas dos Anjos Correia da Silva – RM 552890

## Descrição

Este projeto implementa um sistema de recomendação de planos odontológicos utilizando técnicas de Machine Learning para auxiliar usuários na escolha do plano mais adequado. O sistema coleta informações do usuário (através de perguntas), realiza engenharia de features, treina um modelo Random Forest e recomenda o plano com maior probabilidade de adesão.

**Evoluções em relação à entrega anterior:**

*   Implementação de Análise Exploratória de Dados (EDA) para melhor compreensão dos dados.
*   Refatoração da função `recomendar_plano` para garantir a compatibilidade das features entre treinamento e predição, corrigindo o aviso de `UserWarning`.

## Detalhamento da Arquitetura de IA

### Modelo Utilizado: Random Forest

A arquitetura de IA utilizada é um modelo de **Random Forest**, um algoritmo de aprendizado supervisionado que consiste em um conjunto de árvores de decisão.

**Justificativa:**

*   **Simplicidade e Interpretabilidade:** Random Forests são relativamente fáceis de entender e interpretar, o que é importante para a transparência do sistema.
*   **Desempenho:** Random Forests geralmente fornecem bom desempenho em problemas de classificação com dados complexos e não lineares.
*   **Robustez:** Random Forests são robustos a outliers e ruído nos dados.
*   **Importância das Features:** O modelo fornece uma medida da importância de cada feature, o que ajuda a entender quais fatores são mais relevantes para a recomendação.

**Implementação:**

1.  **Engenharia de Features:** As respostas do usuário e as características dos planos são convertidas em features numéricas (ex: idade, renda, frequência de visitas ao dentista, cobertura de serviços).
2.  **Treinamento:** O modelo Random Forest é treinado com os dados sintéticos gerados (ver seção "Base de Dados"). Utilizamos a biblioteca `scikit-learn` para a implementação do modelo.
    ```python
    modelo = RandomForestClassifier(random_state=42, n_estimators=100, max_depth=5)
    modelo.fit(X_train, y_train)
    ```
3.  **Recomendação:** O modelo treinado é usado para prever a probabilidade de adesão a cada plano, e o plano com maior probabilidade é recomendado ao usuário.

## Base de Dados

Para o treinamento e teste da atual versão do projeto, utilizamos uma **base de dados sintética** gerada através de código Python. A geração de dados sintéticos foi necessária devido à falta de dados reais disponíveis.

**Características da Base de Dados Sintética:**

*   **Número de Amostras:** 200
*   **Features:** Informações demográficas, hábitos de saúde bucal, preferências do usuário e características dos planos odontológicos.
*   **Variável Alvo:** "Aderiu" (Sim/Não), indicando se o usuário simulado aderiria ou não ao plano.

**Observação:** Estamos cientes de que dados sintéticos podem não representar completamente a realidade. Em versões futuras, pretendemos utilizar dados reais para treinar o modelo e melhorar sua precisão.

## Arquitetura do Sistema

O sistema é composto pelos seguintes componentes principais:

1.  **Coleta de Dados:** Interface interativa para coletar informações do usuário (implementada com `input()` e `print()`, podendo ser substituída por uma interface web).
2.  **Engenharia de Features:** Funções para converter as respostas do usuário e as características dos planos em features numéricas adequadas para o modelo de ML. Veja o código na função `criar_features` no arquivo `Tooth_Fairy.ipynb`.
3.  **Modelagem:** Código para treinar e avaliar o modelo Random Forest (implementado com a biblioteca `scikit-learn`).
4.  **Recomendação:** Função `recomendar_plano` que utiliza o modelo treinado para prever a probabilidade de adesão e recomendar o plano mais adequado.
