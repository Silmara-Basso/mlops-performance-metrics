# mlops-performance-metrics
Aplicação  web  para  consumir  o sistema  de  RAG  e  usar  um  LLM  Open-Source  em  um  sistema  de  perguntas  e respostas com monitoração de métricas de performance.


Objetivo foi peracionalizar o uso de aplicações de IA Generativa.
Comecei  construindo um módulo de automação da carga e atualização de um sistema de RAG. Na sequência criei uma aplicação web para consumir o sistema de RAG e usar um LLM Open-Source em um sistema de perguntas e respostas. Por fim, criei um módulo para monitorar em tempo real as métricas e performance da aplicação de IA Generativa.


# Pipeline de MLOps Para Operacionalização e Monitoramento de IA Generativa com LLM e RAG

## Instruções Para Execução do Projeto

### 1- Crie sua conta no HuggingFace, acesse o site abaixo e crie sua chave gratuita (token) para a API:

https://huggingface.co/settings/tokens

### 2- Edite o arquivo abaixo e altere o valor de HUGGINGFACE_KEY para sua chave.

docker-compose.yaml

## 3- Inicialize o Docker Desktop.

### 4- Abra o terminal ou prompt de comando, navegue até a pasta raiz com os arquivos e execute o comando abaixo para criar os containers:

docker compose up --build -d

### Nota: Será preciso editar 2 arquivos e colocar o nome do hostname do container do ElasticSearch nos arquivos llmelasticSearch.py e llm_carrega_dados.py

## 5- Abra o navegador e acesse o Airflow para ativar a DAG:

localhost:8080

username: airflow
password: airflow

### 6- Abra o navegador e acesse a app web para interagir com o LLM (espere alguns segundos até o ElasticSearch finalizar a indexação):

localhost:8501

### Exemplos de perguntas:

Can the landlord avoid liability for breaching this obligation if the state of disrepair is caused by the tenant's actions?
Why did the plaintiff wait seven months to file an appeal?
Can you provide more details on the clarification provided in Note 1?

![App](/images/assistente.png)


### 7- Abra o navegador e acesse o Grafana para carregar o dashboard. Siga as instruções das aulas para ajustar a configuração:

localhost:3000

username: admin
password: admin

# - Crie a Data source - 
Data source - add data source
postgre
<nome do servidor postgre>:5432
user airflow 
senha airflow

TLS/SSL Mode - desable
save & test

# Agora vamos importar e configurar o dashboard
dashboards
create dashboard
import
arrate e solte o arquivo dashboard.json da pasta llmdashboardgrafana
import

Vai exibir como "No Data""
vamos precisar atualizar as fontes clicando nos 3 pontinhos ao lado de cada painel, edit, run query, save dashboard e finalmente save
back to dashboard

repita para todos


### Envie perguntas na app de IA Generativa e monitore pelo Dashboard do Grafana.

![monitoramento](/images/grafana.png)

