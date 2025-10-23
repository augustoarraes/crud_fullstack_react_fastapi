FROM python:3.9.19-alpine

LABEL maintainer="Augusto Arraes <arraes.augusto@gmail.com>"

# set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

WORKDIR /app
 
COPY requirements.txt .

RUN pip install --no-cache-dir --upgrade -r requirements.txt

COPY . .

EXPOSE 5000

# --reload
CMD ["uvicorn", "app.api:app", "--reload", "--host", "0.0.0.0", "--port", "5000"]
