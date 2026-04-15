# Leonardo Torquato

**Engenheiro de Software · Full-Stack · Arquitetura de Sistemas · IA**

Formado em Ciência da Computação (UNIFOR), com experiência em sistemas distribuídos,
motores de visualização 3D, orquestração de agentes de IA e pipelines de dados.

Atualmente Engenheiro de Software na **Cirurgic 3D** (Health Tech) e freelancer
projetando ecossistemas inteligentes com LLMs.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](www.linkedin.com/in/leonardo-lima-b4a20521a)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:leonardotorquato49@gmail.com)

---

## 💼 Experiência Profissional

### 🏥 Cirurgic 3D — Engenheiro de Software

Desenvolvimento full-cycle de uma plataforma que converte exames de imagem médica (DICOM/NIfTI) em modelos tridimensionais interativos, abrangendo desde o upload de arquivos volumosos (~2 GB) até a renderização no browser.

- **Backend:** API assíncrona com FastAPI, SQLAlchemy async (asyncpg) e PostgreSQL, com migrações versionadas via Alembic. Processamento pesado (segmentação 3D, anonimização, reconstrução com VTK/SimpleITK) delegado a workers Celery + Redis, com armazenamento em object storage S3-compatível (Garage/boto3).
- **Frontend & Viewer 3D:** SPA em React 19 / Vite / TypeScript (strict mode) com engine de visualização própria (`c3d-viewer-engine`) baseada em Three.js, React Three Fiber e VTK.js. Internacionalização com i18next e estilização com Tailwind CSS.
- **NephroVision:** Serviço especializado em análise de perfusão renal — Voronoi 3D, centerlines vasculares (VMTK), export GLB — com pipeline científico (NumPy, SciPy, trimesh, nibabel, scikit-image).
- **Infra:** Monorepo orquestrado via Docker Compose (web, API, PostgreSQL, Redis, Celery worker, Garage, MailHog) com CI via GitHub Actions.

### 🤖 Giga+ AI Agents — Desenvolvedor Full-Stack Freelance

Ecossistema de agentes de IA para automatizar o monitoramento, triagem e gestão de licitações públicas, consumindo a API REST do PNCP.

- **Pipeline de Agentes (Scout → Analista → Liaison):** Orquestração sequencial de múltiplos LLMs com contratos tipados PydanticAI e schemas Pydantic como interface entre agentes — zero acoplamento entre módulos, princípios SOLID e hierarquia de exceções customizada.
- **Scout:** Busca e triagem de licitações com scoring de relevância via OpenAI/GPT-4o-mini, scraping adaptativo com Playwright e resiliência com Tenacity (retry + backoff).
- **Analista:** Extração inteligente de editais em PDF com chunking semântico em 3 camadas (pdfplumber + PyMuPDF como fallback) e análise documental via Anthropic/Claude 3.5, produzindo schemas Go/No-Go estruturados.
- **Liaison:** Integração automatizada com Bitrix24 CRM (criação de leads) e WhatsApp via Evolution API, com fluxo de urgência assíncrono (`asyncio.gather`) para licitações em status crítico.
- **Qualidade:** Suíte de testes com pytest-asyncio, mocks com respx, logging estruturado com structlog e modo demo sem dependências externas.

### 📊 Campanha-Sys — Desenvolvedor Full-Stack Freelance

Sistema completo de gestão de campanha eleitoral com CRM de eleitores, comunicação em tempo real e análise geoespacial.

- **Mapeamento Eleitoral:** Processamento de dados do TSE e IBGE com GeoPandas, Shapely e pyproj para geração de mapas estratégicos interativos por bairro via Folium, com auditoria de intenção de voto.
- **Comunicação Real-Time:** Flask-SocketIO (WebSocket com namespaces e rooms por instância) cooperando com sidecar Node.js/Baileys para automação de sessões WhatsApp — dois processos em produção via Heroku (Gunicorn multi-thread).
- **Segurança & RBAC:** Controle de acesso hierárquico (SuperAdmin, Presidente, Candidato, Coordenador), CSP com Flask-Talisman, rate limiting, CSRF, e hashing bcrypt.
- **IA & Integrações:** Estúdio de conteúdo com Google Gemini, integração de pagamentos (InfinitePay via webhooks), engajamento Instagram/TikTok, geração de relatórios PDF (WeasyPrint).
- **Banco de Dados:** Flask-SQLAlchemy com dezenas de migrações Alembic, SQLite em dev e PostgreSQL em produção, com mecanismo de compatibilidade de schema em runtime.

---

## 🚀 Projetos Pessoais

### 📑 Extrator Lattes CNPq — Pipeline ELT

Pipeline de extração massiva de currículos acadêmicos através do protocolo SOAP governamental do CNPq.

- Construção manual de envelopes SOAP (sem Zeep/suds), transporte HTTP com `requests`, parsing de namespaces XML com `lxml`, decodificação Base64 → ZIP → XML com conversão recursiva para dicionários Python.
- Armazenamento como JSONB em PostgreSQL com upsert idempotente e índice GIN, projetado para evoluir em lakehouse com views materializadas.

### 🛒 DistriCommerce — Arquitetura de Microsserviços

Plataforma de e-commerce distribuída simulando o fluxo completo de uma grande varejista.

- **3 Microsserviços Spring Boot** (Java 17/21): Produtos/Usuários (JPA + PostgreSQL), Pedidos/Pagamentos/Logística (MongoDB), com API Gateway (Spring Cloud Gateway + Resilience4j Circuit Breaker + fallback).
- **Mensageria assíncrona** com RabbitMQ (DirectExchange, filas dedicadas, `@RabbitListener`) para o fluxo pedido → pagamento → logística.
- **Observabilidade:** Prometheus + Grafana com métricas via Micrometer/Actuator. Frontend em React/Vite com Material UI.

---

## 🛠️ Stack Tecnológica

**Back-End**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)
![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring&logoColor=white)
![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=for-the-badge&logo=pydantic&logoColor=white)

**Front-End**

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Three.js](https://img.shields.io/badge/Three.js-000000?style=for-the-badge&logo=three.js&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-B73BFE?style=for-the-badge&logo=vite&logoColor=FFD62E)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Material UI](https://img.shields.io/badge/Material_UI-007FFF?style=for-the-badge&logo=mui&logoColor=white)

**IA & LLMs**

![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white)
![Anthropic](https://img.shields.io/badge/Anthropic-191919?style=for-the-badge&logo=anthropic&logoColor=white)
![Google Gemini](https://img.shields.io/badge/Google_Gemini-8E75B2?style=for-the-badge&logo=googlegemini&logoColor=white)

**Banco de Dados & Mensageria**

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-FF6600?style=for-the-badge&logo=rabbitmq&logoColor=white)

**Infraestrutura & Observabilidade**

![Docker](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white)
![Celery](https://img.shields.io/badge/Celery-37814A?style=for-the-badge&logo=celery&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Heroku](https://img.shields.io/badge/Heroku-430098?style=for-the-badge&logo=heroku&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)
