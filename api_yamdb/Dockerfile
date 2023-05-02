FROM python:3.7-slim
RUN mkdir /app
COPY ./ /app
RUN cd app/
RUN ls app/
RUN pip3 install -r /app/api_yamdb/requirements.txt --no-cache-dir
WORKDIR /app/api_yamdb/
CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000"]
