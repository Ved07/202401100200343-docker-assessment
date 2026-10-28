
FROM python:3.12-slim-bookworm

ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1

ARG APP_VERSION=dev
ENV APP_VERSION=${APP_VERSION}

WORKDIR /backend

RUN groupadd --system app && useradd --system --gid app app

COPY requirements.txt .
RUN pip install --no-cache-dir --upgrade pip \
    && pip install --no-cache-dir -r requirements.txt

COPY app.py .

USER app

EXPOSE 5000

CMD ["python", "app.py"]
