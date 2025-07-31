FROM python:3.11-slim

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

WORKDIR /app

RUN apt-get update && apt-get install -y \
    chromium-driver \
    chromium \
    unzip \
    curl \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

ENV CHROME_BIN=/usr/bin/chromium
ENV CHROMEDRIVER_PATH=/usr/bin/chromedriver

# ✅ Copy only contents of Railway-Test to /app
COPY Railway-Test/ /app

RUN pip install --no-cache-dir -r requirements.txt

EXPOSE 8080

# ✅ Run app.py from /app
CMD ["gunicorn", "-b", "0.0.0.0:8080", "app:app"]
