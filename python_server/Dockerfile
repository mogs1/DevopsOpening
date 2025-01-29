#Build Stage 
FROM python:3.11-slim AS builder

WORKDIR /app

COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt


#Final stage
FROM python:3.11-alpine3.21 AS final

WORKDIR /app

COPY --from=builder /usr/local/lib/python3.11/site-packages /usr/local/lib/python3.11/site-packages

COPY  app.py .

CMD [ "python", "app.py" ]