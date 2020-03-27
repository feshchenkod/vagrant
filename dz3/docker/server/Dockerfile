FROM python:3-alpine
RUN apk update && apk upgrade && apk add --no-cache bash git gcc libc-dev curl
RUN addgroup -S otus && adduser -h /home/otus -G otus -S -D otus
WORKDIR /home/otus/server
RUN pip install --upgrade pip
RUN pip install aiohttp
RUN git clone https://gitlab.com/erlong15/websocket-sample.git /home/otus/server
RUN chown -R otus:otus /home/otus/server
USER otus
EXPOSE 8088
HEALTHCHECK --interval=30s --timeout=3s CMD curl --fail http://localhost:8088/ || exit 1
#CMD ["python", "./signal_server.py"]
