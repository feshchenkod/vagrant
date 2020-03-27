FROM python:3-alpine
RUN addgroup -S otus && adduser -h /home/otus -G otus -S -D otus
RUN apk update && apk upgrade && apk add --no-cache bash git gcc libc-dev
WORKDIR /home/otus/client
RUN pip install --upgrade pip
RUN pip install aiohttp
RUN git clone https://gitlab.com/erlong15/websocket-sample.git /home/otus/client
USER otus
#CMD ["python", "./signal_client.py"]
