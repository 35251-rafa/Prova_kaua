# API de Upload e Download de Arquivos

API desenvolvida em Python utilizando o framework **Flask** e banco de dados **SQLite** para gerenciamento de envio e download de arquivos.

## Tecnologias Utilizadas
* Python 3
* Flask
* SQLite3
* Gunicorn (Servidor WSGI para produção)

## Estrutura do Projeto
* `app.py`: Arquivo principal de inicialização da aplicação e registro das rotas.
* `controllers/`: Lógica de negócio para processamento de uploads e downloads.
* `models/`: Camada de comunicação com o banco de dados SQLite.
* `routes/`: Definição dos endpoints da API usando Blueprints.
* `database/`: Configuração e criação da tabela no banco de dados.

## Endpoints da API

### 1. Verificar status da API
* **Rota:** `GET /`
* **Resposta:** Retorna JSON confirmando que a API está online.

### 2. Realizar Upload de Arquivo
* **Rota:** `POST /uploads/upload`
* **Corpo da requisição:** `form-data` com a chave `file` contendo o arquivo.
* **Regras:** 
  * Extensões permitidas: `png`, `jpg`, `jpeg`, `gif`, `pdf`, `txt`.
  * Tamanho máximo: `30 KB`.

### 3. Realizar Download de Arquivo
* **Rota:** `GET /downloads/download/<nome_do_arquivo>`
* **Resposta:** Faz o download do arquivo solicitado caso ele exista no servidor.

## Como executar localmente
1. Instale as dependências:
   ```bash
   pip install -r requirements.txt
   