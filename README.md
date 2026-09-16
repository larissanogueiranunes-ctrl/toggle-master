ToggleMaster

Migração de uma aplicação monolítica para uma arquitetura de microsserviços, containerizada com Docker/Kubernetes e implantada na AWS. Projeto desenvolvido como parte de um University Tech Challenge.

Sobre o projeto

O ToggleMaster nasceu como uma aplicação monolítica e foi migrado, em etapas, para uma arquitetura distribuída de microsserviços independentes. O objetivo do desafio foi aplicar na prática conceitos de containerização, orquestração e infraestrutura como código, partindo de um sistema legado até um ambiente cloud-native pronto para produção.

O projeto foi dividido em duas fases principais:

Fase 1 — Monólito na AWS: deploy da aplicação monolítica original na AWS (VPC, EC2, RDS), seguindo a metodologia 12-Factor App, incluindo estimativa de custos e documentação técnica do processo.

Fase 2 — Migração para microsserviços: decomposição do monólito em serviços independentes, totalmente containerizados, com todos os health endpoints validados.
Arquitetura

O sistema é composto por quatro microsserviços independentes:
Serviço	Responsabilidade
auth-service - Autenticação e controle de acesso
evaluation-service - Avaliação de regras e condições dos feature flags
flag-service - Gerenciamento dos feature flags
targeting-service -	Segmentação e targeting de usuários

Cada serviço é independente, com seu próprio ciclo de build e deploy, se comunicando através de APIs

Tecnologias
Linguagens: Go e Python
Containerização: Docker e Docker Compose
Orquestração: Kubernetes
Persistência: PostgreSQL, Redis, DynamoDB
Cloud: AWS (VPC, EC2, RDS)
Infraestrutura como código: Terraform

Como executar localmente:

Pré-requisitos: Docker e Docker Compose instalados.

bash
# Clone o repositório
git clone https://github.com/larissanogueiranunes-ctrl/toggle-master.git
cd toggle-master

# Suba todos os serviços
docker compose up --build
Consulte o docker-compose.yaml de cada serviço para as variáveis de ambiente, portas e dependências (PostgreSQL, Redis, DynamoDB) necessárias.

Estrutura do projeto
toggle-master/
├── auth-service/
├── evaluation-service/
├── flag-service/
├── targeting-service/
├── docker-compose.yaml
├── dockerfile
└── .gitignore
Status

✅ Containerização completa dos quatro serviços ✅ Health endpoints validados ✅ Projeto publicado no GitHub 🔜 Deploy completo do cluster Kubernetes na AWS
