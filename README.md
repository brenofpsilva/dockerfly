![Logo](https://raw.githubusercontent.com/brenofpsilva/images/refs/heads/main/logo-dockerfly.png)

# 🐳 Dockerfly

Dockerfly é um ambiente Docker pronto para acelerar o início de projetos Laravel, utilizando FrankenPHP como servidor de aplicação, além de MySQL, Redis e Mailpit para um ambiente de desenvolvimento completo.

O objetivo do projeto é fornecer uma base simples, moderna e produtiva, reduzindo o tempo de setup e padronizando o ambiente de desenvolvimento.

## 🚀 Stack utilizada

- FrankenPHP (PHP moderno + servidor embutido)
- MySQL
- Redis
- Mailpit (Captura de e-mails em ambiente local)
- Docker & Docker Compose

## 📁 Estrutura do projeto
```text
dockerfly/
├── .docker/
│   └── Dockerfile        # Imagem do FrankenPHP
├── src/                  # Código da aplicação Laravel
├── docker-compose.yml    # Orquestração dos containers
├── .env                  # Variáveis de ambiente do Docker
└── README.md
```

## 🛠 Pré-requisitos

Antes de iniciar, você precisa ter instalado:

- Docker
- Docker Compose (v2+)

Verifique se está tudo instalado:
```bash
docker --version
docker compose version
```
## ⚙️ Configuração inicial
### 1️⃣ Clone o repositório
```bash
git clone https://github.com/brenofpsilva/dockerfly.git
cd dockerfly
```
### 2️⃣ Configure o arquivo .env

```bash
cp .env.example .env
```

O projeto possui um .env para o Docker. Você pode ajustar portas e credenciais conforme necessário:
```bash
# FrankenPHP
FRANKENPHP_PORT=80
FRANKENPHP_SSL_PORT=443
FRANKENPHP_DEV_PORT=5173

# Mysql
MYSQL_PORT=3306
MYSQL_ROOT_PASSWORD=root_password
MYSQL_DATABASE=dockerfly_db
MYSQL_USER=dockerfly_user
MYSQL_PASSWORD=dockerfly_password

# Redis
REDIS_PORT=6379

# Mailpit
MAILPIT_WEB_PORT=8025
MAILPIT_SMTP_PORT=1025
```
⚠️ **Atenção**: essas variáveis são usadas pelo `docker-compose.yml`, não confundir com o `.env` do Laravel.

## ▶ Subindo o ambiente

Execute o comando abaixo para construir e subir os containers:
```bash
docker compose up -d
```
Isso irá:
- Construir a imagem do FrankenPHP
- Subir os serviços:
  - app (Laravel + FrankenPHP)
  - db (MySQL)
  - redis (Cache)
  - mail (Mailpit)
