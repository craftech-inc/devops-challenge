FROM python:3.7-alpine

ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1
RUN apk update && apk add postgresql-dev gcc python3-dev graphviz graphviz-dev libpq-dev gcc musl-dev

RUN adduser -D userBack
USER userBack
ENV PATH="/home/userBack/.local/bin:${PATH}"


WORKDIR /backend
COPY requirements.txt /backend/
COPY . /backend/

RUN pip install -r requirements.txt
CMD ["python","manage.py","runserver","0.0.0.0:8000"]
