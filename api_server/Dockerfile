FROM python:3.12

LABEL authors="gnir"

RUN apt update && apt install pipx -y && pipx install poetry==1.7.1

RUN echo "export PATH=$PATH:/root/.local/bin/" > ~/.bashrc

RUN mkdir -p /app/api_server

WORKDIR /app/api_server

COPY ./poetry.lock ./pyproject.toml ./README.md /app/api_server/

RUN /root/.local/bin/poetry install

COPY ./api_server /app/api_server/api_server

ENTRYPOINT ["/root/.local/bin/poetry", "run", "uvicorn", "api_server.server:app", "--host", "0.0.0.0", "--port", "8000"]