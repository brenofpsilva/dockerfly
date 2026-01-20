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
