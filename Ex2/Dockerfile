FROM python:3.8 AS builder
COPY requirements.txt .
RUN pip install --user -r requirements.txt
FROM python:3.8-slim
COPY --from=builder /root/.local /root/.local
ENV PATH=/root/.local:$PATH
ADD  app.py /
CMD [ "python3", "-u", "./app.py" ]
