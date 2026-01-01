
FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

# debugpyを使ってデバッグ可能にする
CMD ["python3", \
    "-m", "debugpy", "--listen", "0.0.0.0:5678", "--wait-for-client", \
    "-m", "uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000", "--reload"]
