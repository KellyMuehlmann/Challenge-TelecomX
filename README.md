Análise de Evasão de Clientes (Churn Analysis)

Visão Geral do Projeto
Este projeto realiza uma análise completa da evasão de clientes (churn) de uma empresa de telecomunicações. O objetivo é identificar os principais fatores que levam os clientes a cancelar seus serviços e fornecer insights para a criação de estratégias de retenção mais eficazes.

Dados
O conjunto de dados utilizado neste projeto é proveniente da [URL do dataset]. Ele contém informações sobre clientes, incluindo dados demográficos, serviços contratados e histórico de cobrança.

As principais colunas incluem:

customerID: Identificador único do cliente.
Churn: Indica se o cliente cancelou o serviço ('Yes') ou não ('No').
customer.*: Informações demográficas do cliente (gênero, idade, parceiro, dependentes, tempo de cliente).
phone.*: Informações sobre o serviço telefônico.
internet.*: Informações sobre o serviço de internet.
account.*: Informações da conta (contrato, cobrança, método de pagamento, encargos).
Metodologia
A análise seguiu as seguintes etapas:

Carregamento e Normalização de Dados: Os dados em formato JSON foram carregados e transformados em um DataFrame tabular utilizando a biblioteca pandas.
Limpeza e Tratamento de Dados:
Identificação e tratamento de valores vazios e inconsistentes na coluna 'Churn'.
Conversão da coluna 'account.Charges.Total' para tipo numérico, tratando valores que não puderam ser convertidos.
Criação da nova feature 'Total.Day' (encargo médio diário) a partir dos encargos totais e tempo de cliente.
Remoção de linhas com valores ausentes (NaN) nas colunas relevantes após a criação da feature 'Total.Day' e divisão dos dados.
Análise Exploratória de Dados (EDA): Análise visual e estatística para entender as características dos clientes e a relação entre as variáveis e o Churn. Foram utilizados histogramas, box plots e gráficos de linha para visualizar distribuições, identificar padrões e calcular a taxa de churn por tempo de cliente.
Preparação para Modelagem: Aplicação de one-hot encoding em variáveis categóricas para prepará-las para a modelagem preditiva. Os dados foram divididos em conjuntos de treino e teste para o desenvolvimento e avaliação de um modelo de Machine Learning.
Principais Achados da Análise Exploratória
A análise exploratória revelou insights importantes sobre os fatores que mais contribuem para o churn:

Tempo de Cliente (Tenure): Clientes com menor tempo de contrato (< 1 ano) apresentam uma taxa de churn significativamente maior. A taxa de churn diminui consideravelmente à medida que o tempo de cliente aumenta.
Tipo de Contrato: Clientes com contratos de 'Month-to-month' (mês a mês) têm uma probabilidade muito maior de churn em comparação com aqueles com contratos de um ou dois anos.
Serviço de Internet: Clientes que utilizam serviço de 'Fiber optic' (Fibra Óptica) parecem ter uma taxa de churn mais alta do que aqueles com DSL ou sem serviço de internet.
Método de Pagamento: O método de pagamento 'Electronic check' (cheque eletrônico) está associado a uma maior taxa de churn.
Serviços Adicionais: Clientes que não utilizam serviços adicionais como segurança online, backup online, proteção de dispositivo e suporte técnico tendem a ter maior probabilidade de churn.
Encargos: Os encargos mensais e totais, assim como o encargo diário calculado, também mostram diferenças entre clientes que evadem e os que não evadem.
Próximos Passos (Modelagem Preditiva)
Para aprofundar a análise e prever o churn, os próximos passos incluem:

Treinamento do Modelo: Treinar um modelo de classificação (por exemplo, Regressão Logística) com os dados preparados.
Avaliação do Modelo: Avaliar o desempenho do modelo usando métricas como acurácia, precisão, recall e F1-score.
Interpretação do Modelo: Analisar a importância das features (variáveis) no modelo para confirmar os insights da EDA e identificar outros fatores relevantes.
Como Reproduzir o Projeto
Para reproduzir esta análise:

Clone este repositório para o seu ambiente local.
Certifique-se de ter as bibliotecas Python necessárias instaladas (pandas, requests, plotly, scikit-learn). Você pode instalá-las usando pip:
