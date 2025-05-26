# SoftSolutions - Docker Compose

Este repositório oferece uma solução completa para execução local da aplicação SoftSolutions utilizando Docker Compose, proporcionando um ambiente de desenvolvimento integrado e de fácil configuração.

A aplicação SoftSolutions é composta por dois serviços principais:
- 🟦 **Backend:** API desenvolvida em NestJS com banco de dados PostgreSQL integrado
- 🟦 **Frontend:** Interface de usuário em Angular servida através de NGINX

---

## 🚀 Como executar localmente

### ✅ Pré-requisitos

- Docker instalado
- Docker Compose instalado

---

## 🔗 Estrutura dos containers

| Serviço   | Porta Local | Descrição                          |
|-----------|-------------|-------------------------------------|
| Frontend  | 4200        | Interface Angular via NGINX        |
| Backend   | 4000        | API NestJS + PostgreSQL embutido   |

---

## 📦 Estrutura de pastas

```
softsolutions-docker/
├── docker-compose.yml          # Orquestração dos containers
├── README.md                    # Este arquivo
├── api-softsolutions/           # Pasta que contém o .env do backend
│   └── .env                     # Variáveis de ambiente do backend (local)
```

> ⚠️ O arquivo `.env` do backend **fica dentro da pasta `api-softsolutions`** e **NÃO é enviado ao GitHub** (já está no `.gitignore`).

---

## 🧠 Como rodar

1️⃣ Clone este repositório:

```bash
git clone https://github.com/SoftSolutionsProject/softsolutions-docker.git
cd softsolutions-docker
```

2️⃣ Crie o arquivo de variáveis de ambiente do backend:

```bash
# Caminho: ./api-softsolutions/.env
```

Exemplo de `.env`:

```env
DATABASE_URL=postgresql://usuario:senha@host:porta/database
JWT_SECRET=sua_chave_secreta
EMAIL_SUPPORT_USER=seu_email@gmail.com
EMAIL_SUPPORT_PASS=sua_senha
EMAIL_SUPPORT_DESTINATION=destino@gmail.com
```

3️⃣ Execute os containers:

```bash
docker compose up -d
```

---

## 🌐 Acesse os serviços

- Frontend ➡️ http://localhost:4200
- Backend ➡️ http://localhost:4000

---

## 🔗 Integração Frontend ↔ Backend

Ao acessar o frontend em:

```
http://localhost:4200
```

A aplicação Angular se comunica automaticamente com o backend, disponível em:

```
http://localhost:4000
```

Ambos os serviços estão rodando como containers Docker, utilizando imagens públicas hospedadas no Docker Hub:

- 🐳 Backend: `softsolutionsfatecvotorantim/api-softsolutions:latest`
- 🐳 Frontend: `softsolutionsfatecvotorantim/front-softsolutions:latest`

> ✅ A comunicação entre frontend e backend já está totalmente configurada, simulando um ambiente real de produção, sem necessidade de configurações adicionais. Basta executar:

```bash
docker compose up -d
```

---

## 🛠️ Comandos úteis

| Comando                                  | Descrição                              |
|-------------------------------------------|-----------------------------------------|
| docker compose up -d                      | Inicia os containers                   |
| docker compose down                       | Para e remove os containers            |
| docker compose logs -f backend            | Ver logs do backend                    |
| docker compose logs -f frontend           | Ver logs do frontend                   |
| docker ps                                 | Ver containers rodando                 |
| docker compose stop                       | Pausa os containers                    |
| docker compose start                      | Retoma containers pausados             |

---

## 📄 Observações importantes

- ✅ O banco de dados PostgreSQL está embutido no backend (não há container separado).
- ✅ As imagens estão publicadas no Docker Hub:

| Serviço   | Imagem no Docker Hub                                      |
|-----------|-----------------------------------------------------------|
| Backend   | `softsolutionsfatecvotorantim/api-softsolutions:latest`   |
| Frontend  | `softsolutionsfatecvotorantim/front-softsolutions:latest` |

- 🔐 O arquivo `.env` deve ser criado manualmente na pasta `api-softsolutions` e **não deve ser enviado para o GitHub**.

---
