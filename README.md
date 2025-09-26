# n8n e Ollama com Docker

Este projeto configura e executa instâncias do n8n e do Ollama utilizando Docker e Docker Compose, com arquivos de configuração separados para cada serviço.

## Pré-requisitos

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Como Executar

Certifique-se de que o Docker Desktop está em execução antes de rodar os comandos.

### n8n

1.  **Iniciar o n8n:**
    ```bash
    docker-compose -f n8n.yml up -d
    ```

2.  **Acessar o n8n:**
    - **URL:** [http://localhost:5678](http://localhost:5678)
    - **Usuário:** `admin`
    - **Senha:** `admin`

3.  **Parar o n8n:**
    ```bash
    docker-compose -f n8n.yml down
    ```

### Ollama

1.  **Iniciar o Ollama:**
    ```bash
    docker-compose -f ollama.yml up -d
    ```

2.  **Acessar a Interface Web do Ollama:**
    - **URL:** [http://localhost:3000](http://localhost:3000)

3.  **Baixar Modelos de LLM:**
    Após iniciar o Ollama, abra outro terminal e execute os seguintes comandos para baixar os modelos desejados:

    - **DeepSeek R1:**
      ```bash
      docker exec -it ollama ollama pull deepseek-r1
      ```
    - **Gemma 3:**
      ```bash
      docker exec -it ollama ollama pull gemma3
      ```
    - **LLaMA 3.2:**
      ```bash
      docker exec -it ollama ollama pull llama3.2
      ```

4.  **Parar o Ollama:**
    ```bash
    docker-compose -f ollama.yml down
    ```
