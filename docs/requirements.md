# Desafio

## 🔧 **Parte 1 – Uso e Customização do Prowler**

**Objetivo:**
Demonstrar que você sabe usar o **Prowler**, uma ferramenta de auditoria de segurança em contas AWS.

### ✅ O que você deve fazer

1. **Instalar e configurar:**

   * Instale e configure o **AWS CLI** com suas credenciais.
   * Instale o **Prowler CLI** (veja o [repositório oficial do Prowler](https://github.com/prowler-cloud/prowler)).

2. **Executar um Scan Básico:**

   * Rode um comando Prowler para escanear sua conta AWS.

3. **Gerar um Relatório:**

   * Produza um **arquivo de relatório** (pode ser em JSON ou CSV).

4. **Analisar os Resultados:**

   * Identifique os **achados de severidade alta (high-severity)**.
   * Explique **quais são os problemas** encontrados e **como corrigir** cada um.

### 📦 Entregáveis

* Comandos usados no terminal.
* Arquivo de relatório (`.json` ou `.csv`).
* Documento com:

  * Lista dos problemas de alta severidade.
  * Possíveis correções para cada problema.

## 💻 **Parte 2 – Aplicação CRUD com Django REST + Prowler**

**Objetivo:**
Criar uma aplicação Django REST que:

* Gerencie *scans*, *checks* e *findings* do Prowler.
* Permita executar e acompanhar *scans* em tempo real.

### ✅ O que você deve implementar

1. **Projeto Django:**

   * Crie um novo projeto e um novo app Django.

2. **Modelos:**

   * `Scan`: status (pending, in\_progress, etc), timestamps (start/end).
   * `Check`: vinculado a `Scan`.
   * `Finding`: vinculado a `Check`.

3. **API com Django REST Framework:**

   * Endpoints CRUD para Scan, Check e Finding.
   * Endpoint especial: `/scans/<scan_id>/status/` para mostrar status em tempo real.

4. **Execução assíncrona:**

   * Usar **Celery + Redis** para executar os *scans* em background.
   * Garantir que múltiplos *scans* possam rodar em paralelo.

5. **Status em tempo real (opcional):**

   * Pode ser via *polling* ou com **Django Channels** (WebSocket).

6. **Serializers e Viewsets:**

   * Um para cada modelo.
   * O `ScanSerializer` deve mostrar o status em tempo real.

7. **Routing:**

   * Rotas REST para todos os endpoints acima.

### 📦 Entregáveis - 2

* Código-fonte completo do projeto.
* README explicando:

  * Como configurar e rodar o projeto.
  * Como rodar o Celery, Redis e o Prowler.
  * Como usar os endpoints e observar os status dos *scans*.
* Qualquer explicação extra que ache importante.

### 🏢 **Parte 3 – Aplicação Django Multi-Tenant**

**Objetivo:**
Projetar uma aplicação Django com **suporte a múltiplos tenants**, cada um com seus próprios dados (multi-tenancy).

#### ✅ O que você deve **explicar (não precisa codar)**

1. **Arquitetura de Multi-Tenancy:**

   * Como você separaria os dados de cada tenant.
   * Estratégia de schema (ex: schema por tenant ou dados filtrados com identificador).

2. **Ferramentas/Pacotes:**

   * Ex: [`django-tenants`](https://github.com/django-tenants/django-tenants), [`django-tenant-schemas`](https://github.com/bernardopires/django-tenant-schemas).

3. **Banco de Dados:**

   * Usar **PostgreSQL**.
   * Como ele se integra com multi-tenancy.

4. **Desafios e soluções:**

   * Segurança (vazamento de dados entre tenants).
   * Migrações.
   * Performance com muitos tenants.
   * Escalabilidade e manutenção.

### 📦 Entrega

* **PDF** com explicação bem estruturada.
* Pode incluir diagramas, esquemas, referências e links.

### 📌 Dicas Gerais para todas as partes

* Sempre **explique suas decisões** técnicas.
* Use boas práticas de escrita e documentação.
* Comente o código quando necessário.
* O foco está tanto na **implementação** quanto na **clareza da explicação**.
