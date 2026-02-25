FROM python:3.12-slim

WORKDIR /app

RUN useradd -r -s /bin/false appuser

COPY app.py .

RUN chown appuser:appuser /app/app.py

USER appuser

EXPOSE 8080

HEALTHCHECK --interval=30s --timeout=5s --retries=3 \
    CMD python -c "import urllib.request; urllib.request.urlopen('http://localhost:8080/')" || exit 1

CMD ["python", "app.py"]
