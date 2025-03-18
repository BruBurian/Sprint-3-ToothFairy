# Sprint-3-ToothFairy
Este projeto implementa um sistema de recomendação de planos odontológicos utilizando técnicas de Machine Learning. O sistema coleta dados do usuário, realiza engenharia de features, treina um modelo Random Forest e recomenda o plano mais adequado. O repositório inclui:

### Código para geração de dados sintéticos.

### Funções para engenharia de features.

### Código para treinamento e avaliação do modelo.

### Análise exploratória de dados (EDA).

### Função de recomendação.

Este projeto implementa um sistema de recomendação de planos odontológicos utilizando técnicas de Machine Learning. O sistema coleta informações do usuário (através de perguntas), realiza engenharia de features, treina um modelo Random Forest e recomenda o plano mais adequado com base na probabilidade de adesão.

O objetivo principal é auxiliar usuários na escolha do plano odontológico que melhor atenda às suas necessidades e preferências, considerando fatores como:

*   Informações demográficas (idade, renda)
*   Hábitos de saúde bucal (frequência de visitas ao dentista)
*   Necessidades específicas (interesse em ortodontia, clareamento)
*   Orçamento disponível

## Arquitetura do Sistema

O sistema é composto pelos seguintes componentes principais:

1.  **Coleta de Dados:** Interface interativa para coletar informações do usuário.
2.  **Engenharia de Features:** Conversão das respostas do usuário e das características dos planos em features numéricas.
3.  **Modelagem:** Treinamento de um modelo Random Forest para prever a probabilidade de adesão a cada plano.
4.  **Recomendação:** Seleção e apresentação do plano com maior probabilidade de adesão.
