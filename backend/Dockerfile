FROM python:3.10-slim

WORKDIR /app

COPY pyproject.toml poetry.lock /app/

RUN pip install --default-timeout=100 poetry && \
    poetry config virtualenvs.create false && \
    poetry install --no-root

COPY . /app

CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]
