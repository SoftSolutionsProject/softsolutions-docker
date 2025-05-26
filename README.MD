# SoftSolutions - Docker Compose

Este repositório permite executar localmente a aplicação SoftSolutions, composta por:

- Backend (NestJS com PostgreSQL integrado)
- Frontend (Angular servido com NGINX)

## Como executar localmente

### Pré-requisitos:

- Docker instalado
- Docker Compose instalado

## Estrutura dos containers

| Serviço  | Porta Local | Descrição                     |
|----------|-------------|-------------------------------|
| Frontend | 4200        | Interface Angular (NGINX)     |
| Backend  | 4000        | API NestJS + PostgreSQL       |

## Como rodar

1. Clone este repositório:

git clone caminho/local
cd softsolutions-docker

2. Rode o docker-compose:

docker-compose up -d

Pronto.

## Acesse:

- Frontend: http://localhost:4200
- Backend: http://localhost:4000

## Estrutura do projeto:

softsolutions-docker/
├── docker-compose.yml
├── README.md
└── .env (opcional - uso local)

## Variáveis de ambiente (opcional com .env)

Se quiser, pode criar um arquivo `.env` (opcional) e mapear variáveis usadas no backend e frontend.

Exemplo:

BACKEND_PORT=4000
FRONTEND_PORT=4200

## Comandos úteis:

docker-compose up -d                 # Inicia os containers
docker-compose down                  # Para e remove os containers
docker-compose logs -f backend       # Logs do backend
docker-compose logs -f frontend      # Logs do frontend
docker ps                            # Ver containers rodando
docker-compose stop                  # Pausa os containers
docker-compose start                 # Continua containers pausados

## Observações

- Este ambiente é focado em desenvolvimento local.
- O banco de dados PostgreSQL está rodando integrado no backend.
- As imagens frontend e backend estão publicadas no Docker Hub:

Backend: softsolutionsfatecvotorantim/api-softsolutions:latest
Frontend: softsolutionsfatecvotorantim/front-softsolutions:latest

## Pronto para usar.
