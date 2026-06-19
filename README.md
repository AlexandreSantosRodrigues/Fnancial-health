💰 Sistema de Inteligência de Tesouraria e Previsão de Liquidez (SIT-PL)
📌 Visão Geral
O SIT-PL é um pipeline completo de Engenharia e Ciência de Dados construído para transformar a gestão financeira de uma empresa. Ele abandona a visão retroativa (olhar para o que já foi gasto) e implementa uma estratégia preditiva e acionável.

Utilizando algoritmos de Aprendizado de Máquina (Supervisionado e Não-Supervisionado) e Séries Temporais, o sistema ingere transações financeiras brutas e entrega recomendações cirúrgicas de corte de custos e injeção de capital.

🚀 Arquitetura e Funcionalidades do Projeto
O sistema é dividido em 4 módulos principais:

1. ⚙️ Motor de Ingestão e ETL Resiliente
Auto-Correção Temporal: Módulo de leitura inteligente que detecta variações no padrão de datas (ex: padrão americano vs brasileiro) e formatações inconsistentes no CSV.

Classificação de Fluxo: Separação automatizada da natureza da transação (Entradas vs. Saídas) lidando com registros ausentes ou nulos.

2. 📈 Previsão de Descasamento (Séries Temporais)
Algoritmo: Suavização Exponencial de Holt-Winters.

Objetivo: Analisa sazonalidade (ex: picos de pagamento às sextas-feiras) e projeta o Fluxo de Caixa Diário e o Índice de Liquidez para os próximos 7 dias.

Impacto: Alerta a tesouraria sobre a necessidade exata de capital antes que a conta entre no cheque especial.

3. 🔍 Auditoria de Custos com Inteligência Artificial (Clustering)
Algoritmo: K-Means (Aprendizado Não-Supervisionado).

Objetivo: Mapeia todos os fornecedores e centros de custo (AccountID) baseando-se na frequência de saques e volume financeiro drenado.

Impacto: Isola e identifica os "Predadores de Capital" (Cluster 4), gerando uma lista exata de quais contratos devem ser renegociados imediatamente para estancar a hemorragia de caixa.

4. 🛡️ Score de Risco Nativo para Recebíveis (Classificação)
Algoritmo: Random Forest Classifier (Aprendizado Supervisionado).

Objetivo: Analisa o "DNA" de pagamento de cada cliente (frequência, ticket médio, histórico de atrasos) para prever a Probabilidade de Inadimplência.

Impacto: Gera uma "Lista de Ouro" com os clientes de altíssimo ticket e risco quase zero, ideais para campanhas de antecipação de recebíveis, injetando caixa a um custo muito menor que as taxas bancárias.

🛠️ Tecnologias Utilizadas
Linguagem: Python

Processamento e ETL: pandas, numpy

Machine Learning: scikit-learn (K-Means, Random Forest)

Séries Temporais e Estatística: statsmodels

Visualização de Dados (Dashboards): matplotlib, seaborn

Automação de Relatórios: xlsxwriter

⚙️ Como Executar o Projeto
Pré-requisitos
Certifique-se de ter o Python 3.8+ instalado e instale as dependências via pip:

Bash
pip install pandas numpy scikit-learn statsmodels matplotlib seaborn xlsxwriter
Configuração dos Dados
O sistema espera um arquivo .csv contendo as seguintes colunas mínimas: TransactionID, AccountID, Timestamp (ou Date/Data), TransactionType (deposit, withdrawal, payment, transfer) e TransactionAmount.

Altere a variável de ambiente no script principal para apontar para o seu dataset:

Python
CAMINHO_DO_ARQUIVO = './dados/Financial_Transactions.csv'
Execução
Rode o pipeline em blocos (se estiver usando Jupyter Notebook/Kaggle) ou execute o script mestre Python. O sistema compilará os modelos e, ao final, irá:

Plotar os Dashboards Analíticos na tela.

Gerar o arquivo Relatorio_Tesouraria_Acao_Imediata.xlsx na sua pasta raiz.

📊 Entregável Executivo (Relatório Automatizado)
O script final empacota toda a inteligência artificial em um arquivo Excel limpo e direto, dividido em duas abas táticas para a diretoria:

Aba 1 (Cortes Urgentes): Traz o AccountID, frequência e o valor drenado pelos Predadores de Capital identificados pelo K-Means.

Aba 2 (Antecipação Ouro): Lista os clientes com Risco de Atraso < 10% classificados pela Random Forest, recomendados para antecipação de títulos.

🧠 Autores e Especialistas
Projeto desenvolvido sob a ótica de Engenharia e Ciência de Dados Aplicada a Negócios. Focado em extrair valor financeiro direto através de matemática estatística avançada e algoritmos de Machine Learning.

Para dúvidas, otimizações ou escalabilidade em Cloud (AWS/GCP), consulte a documentação técnica ou abra uma issue.
