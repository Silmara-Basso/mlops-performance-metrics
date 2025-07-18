# Pipeline de MLOps Para Operacionalização e Monitoramento de IA Generativa com LLM e RAG

# Define a imagem base com Python
FROM python:3.11

# Define o diretório de trabalho dentro do container
WORKDIR /app

# Copia o arquivo requirements.txt para o diretório de trabalho no container
COPY requirements.txt .

# Instala as dependências listadas em requirements.txt, sem cache para reduzir o tamanho da imagem
RUN pip install --no-cache-dir -r requirements.txt

# Copia todos os arquivos do diretório atual no host para o diretório de trabalho do container
COPY . .

# Define o comando padrão para iniciar o Streamlit e executar a app localizado em streamlit/appllm.py
CMD ["streamlit", "run", "streamlit/appllm.py"]
