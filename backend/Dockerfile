FROM python:3.13.2

RUN apt update && apt install -y wireguard iproute2 iputils-ping net-tools

WORKDIR /v1/src

COPY requirements.txt .
RUN pip install --no-cache-dir --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 8000

CMD ["uvicorn", "v1.src.main:app", "--host", "0.0.0.0", "--port", "8000", "--reload"]
