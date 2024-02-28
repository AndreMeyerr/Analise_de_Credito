# Análise de Crédito - Projeto de Machine Learning

## Descrição do Projeto
Este projeto visa desenvolver um modelo de machine learning para prever a aprovação de crédito com base em várias características dos solicitantes. Utilizamos um conjunto de dados que inclui informações pessoais e financeiras dos solicitantes, juntamente com o status de aprovação do empréstimo (aprovado/não aprovado).

## Dados
O dataset contém as seguintes colunas:
- `Loan_ID`: Identificador único do empréstimo
- `Gender`: Gênero do solicitante
- `Married`: Estado civil
- `Dependents`: Número de dependentes
- `Education`: Nível de educação
- `Self_Employed`: Se o solicitante é autônomo
- `ApplicantIncome`: Renda do solicitante
- `CoapplicantIncome`: Renda do co-solicitante
- `LoanAmount`: Quantia do empréstimo solicitado
- `Loan_Amount_Term`: Prazo do empréstimo em meses
- `Credit_History`: Histórico de crédito
- `Property_Area`: Área da propriedade
- `Loan_Status`: Status de aprovação do empréstimo (Alvo)

## Preparação dos Dados
### Limpeza e Imputação de Dados
- Exclusão de linhas com valores nulos em colunas não essenciais.
- Preenchimento dos valores nulos da coluna `LoanAmount` com a média.
- Imputação dos valores nulos nas colunas `Credit_History`, `Self_Employed` e `Dependents` utilizando o método KNN.

### Codificação de Variáveis Categóricas
- Convertido variáveis categóricas em numéricas usando `pd.get_dummies`, facilitando a modelagem.

### Separação em Conjuntos de Treino e Teste
- Dados divididos em conjuntos de treino e teste com 70% para treino e 30% para teste, utilizando `random_state` para garantir reprodutibilidade.

## Modelo de Machine Learning
- Utilizamos a Regressão Logística como nosso modelo de predição. O modelo foi ajustado com um `max_iter` de 200 para garantir a convergência.

## Avaliação do Modelo
- Avaliamos o desempenho do modelo usando várias métricas: Acurácia, Precisão, Recall, F1-Score, e AUC-ROC. Também foi gerada uma Matriz de Confusão.

## Resultados e Conclusões
- O modelo demonstrou um desempenho robusto em várias métricas-chave. A acurácia do modelo foi elevada, sugerindo uma alta proporção de previsões corretas no geral. A precisão apresentou-se moderada, o que indica que há uma quantidade considerável de falsos positivos; esta é uma área que pode requerer atenção, pois cada falso positivo pode representar um risco financeiro. O recall foi excepcionalmente alto, mostrando que o modelo é muito eficaz em identificar candidatos que são viáveis para aprovação de crédito, o que é essencial em cenários onde é crítico não negar crédito inapropriadamente. O F1 Score, que é a média harmônica entre precisão e recall, também foi forte, refletindo um equilíbrio efetivo entre estas duas métricas. Além disso, o escore AUC-ROC foi sólido, o que significa que o modelo tem uma boa capacidade de diferenciar entre as classes positivas e negativas.

Embora o modelo tenha mostrado um forte desempenho em termos de recall, há espaço para melhorar a precisão. Especialmente em contextos onde o custo dos falsos positivos é alto, estratégias como ajustar o limiar de decisão, refinar a engenharia de recursos, ou explorar modelos mais complexos podem ser benéficas. 

## Futuras Direções
- Explorar modelos mais complexos como Random Forest e Gradient Boosting.
- Realizar análise aprofundada das variáveis para identificar oportunidades de engenharia de recursos.
- Implementar técnicas de balanceamento de classes.

