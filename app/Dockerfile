
FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

# # 本番用
# CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000", "--reload"]

# デバッグ実行用
EXPOSE 5678
CMD ["python3", \
    "-m", "debugpy", "--listen", "0.0.0.0:5678", "--wait-for-client", \
    "-m", "uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000", "--reload"]
