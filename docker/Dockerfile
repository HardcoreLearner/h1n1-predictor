FROM python:3.10-slim

WORKDIR /app

# Installation minimale
RUN apt-get update && apt-get install -y --no-install-recommends \
    gcc \
    python3-dev \
    && rm -rf /var/lib/apt/lists/*

# Copie uniquement requirements.txt d'abord
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copie le reste après l'installation
COPY . .

CMD ["mlflow", "server", "--host", "0.0.0.0"]