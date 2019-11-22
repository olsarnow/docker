FROM python:3.5
RUN pip install Flask==0.11.1
RUN useradd -ms /bin/bash james
USER james
WORKDIR /app
COPY app /app
CMD ["python", "app.py"]
