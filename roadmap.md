# Roadmap - Sistema de Gestão Corporativo

Fases essenciais para o desenvolvimento do sistema de gestão, inclui desde a modelagem do banco de dados até o deploy e manutenção dos ambientes web e mobile.

> As Fases 1, 2 e 3 acontecem em conjunto pensando em modificar a lógica básica.

> As Fases 4 e 5 também acontecem em conjunto, pro designer não dar ideias absurdas muito difíceis de fazer.

---

## Fase 1: Levantamento e Planejamento
- **Reuniões com Stakeholders:** Definir objetivos e identificar os principais requisitos (Se você está lendo isso, já demos o primeiro passo).
- **Definição de Escopo e MVP:** Documentar todas as funcionalidades essenciais.
- **Criação do Backlog:** Elaboração de histórias de usuário e dos casos de uso (Facilita a vida do Designer). 

---

## Fase 2: Modelagem de Dados e Banco de Dados
- **Modelos Conceituais:**
  - Definição dos modelos de entidades (Empresas, Usuários, Projetos, Clientes, Sprints, Repositórios, Acessos).
  - Criação do Diagrama Entidade-Relacionamento (ER).
- **Banco de Dados Relacional:**
  - Escolha do SGBD: PostgreSQL ou MySQL.
  - Desenvolvimento dos scripts SQL para criação de tabelas e índices.
  - Configuração da camada de ORM com **SQLAlchemy** - Python.

---

## Fase 3: Definição das Funcionalidades do MVP
- **Funcionalidades Principais:**
  - **Sistema de Autenticação:**
    - Implementação de autenticação e autorização via tokens (JWT ou Paseto).
  - **Gestão de Empresas e Usuários:**
    - Cadastro, edição, remoção e gerenciamento de hierarquia de papéis e cargos.
  - **Gestão de Projetos e Clientes:**
    - Criação, edição, exclusão de projetos e associação com clientes/contratos (many-to-many).
  - **Gestão de Sprints e Repositórios:**
    - Planejamento e acompanhamento de sprints.
    - Integração com GitHub para monitoramento de repositórios (Github tem API pra isso?).
  - **Gerenciamento de Acessos:**
    - Controle de acessos a VPSs e contas, com armazenamento criptografado de credenciais.
    - Notificações automáticas para remoção indevida de gerentes.
  - **Integração com Sistemas Externos:**
    - Conexão segura com APIs (GitHub e futuros microsserviços com LLMs).

- **Documentação dos Endpoints e Casos de Uso:**
  - Lista detalhada de endpoints GraphQL (com suporte REST complementar).
  - Documentação de modelos e serviços para orientar a equipe de desenvolvimento (Essas documentações o FastAPI faz, só precisamos aperfeiçoar).

---

## Fase 4: Design e Prototipação Visual
- **Identidade Visual:**
  - Definição da paleta de cores, tipografia e guidelines visuais.
- **Prototipação no Figma:**
  - Criação de protótipos de alta fidelidade para todas as telas.
  - Validação dos fluxos de navegação e interfaces com stakeholders e equipe de design.
- **Documentação dos Componentes de UI:**
  - Especificação de elementos de interface e interações para auxiliar os desenvolvedores.

---

## Fase 5: Desenvolvimento do Backend
- **Ambiente de Desenvolvimento:**
  - Configuração do ambiente com **Python**, **FastAPI** e **Strawberry GraphQL**.
- **Estrutura do Projeto:**
  - Organização dos diretórios e definição dos módulos:
    - **Endpoints/API:** Criação dos resolvers GraphQL e endpoints REST.
    - **Models:** Definição das entidades utilizando SQLAlchemy.
    - **Services:** Implementação da lógica de negócio e integração com sistemas externos.
    - **Autenticação:** Desenvolvimento do sistema de autenticação e autorização (JWT/Paseto).
- **Integração e Testes:**
  - Integração contínua com serviços externos (ex.: GitHub).
  - Desenvolvimento de testes unitários e de integração.
  - Documentação completa da API (Swagger/OpenAPI e documentação interna).

---

## Fase 6: Desenvolvimento do Frontend Web
- **Configuração do Ambiente Next.js:**
  - Instalação e configuração inicial do projeto.
- **Desenvolvimento das Páginas Essenciais:**
  - **Landing Page:** Apresentação do sistema e informações gerais.
  - **Login e Cadastro:** Formulários de autenticação e registro de usuários.
  - **Dashboard/Index:** Visão geral com informações de acesso rápido.
  - **CRUD de Empresas, Clientes, Projetos e Membros:** 
    - Páginas para criação, leitura, atualização e remoção.
    - Detalhamento dos papéis e permissões.
  - **Outras Páginas:** Perfil do usuário, configurações, notificações e suporte.
- **Integração com a API:**
  - Consumo da API GraphQL para operações de dados.
- **Testes e Validação:**
  - Testes de usabilidade, responsividade e performance.

---

## Fase 7: Desenvolvimento do Frontend Mobile
- **Configuração do Ambiente Flutter:**
  - Instalação e configuração inicial do projeto mobile.
- **Desenvolvimento das Telas Essenciais:**
  - **Splash e Onboarding:** Primeiras telas de apresentação e configuração.
  - **Login e Cadastro:** Formulários de autenticação para mobile.
  - **Dashboard/Index:** Interface principal com informações resumidas.
  - **CRUD de Empresas, Clientes, Projetos e Membros:** 
    - Páginas para gestão e manutenção dos dados.
  - **Funcionalidades Específicas:** 
    - Notificações em tempo real, acesso a funcionalidades críticas e integração com serviços externos.
- **Integração com a API:**
  - Conexão com a API GraphQL para operações de dados.
- **Testes e Ajustes:**
  - Testes de performance, usabilidade e compatibilidade (iOS/Android).

---

## Fase 8: Infraestrutura e Deploy
- **Containerização e Orquestração:**
  - Containerização do sistema utilizando **Podman**.
  - Orquestração via **Kubernetes** para gerenciamento escalável dos containers.
- **Configuração do Balanceador de Carga:**
  - Implementação do **Nginx** para distribuição das requisições.
- **Ambiente de Produção:**
  - Configuração de VPS com IP público, SSL, e domínio próprio.
- **Pipeline de CI/CD:**
  - Criação de pipelines para deploy contínuo e integração contínua (CI/CD).
- **Monitoramento e Logs:**
  - Configuração de ferramentas de monitoramento (ex.: Prometheus, Grafana) e gestão de logs.

---

## Fase 9: Monitoramento, Manutenção e Feedback
- **Monitoramento Contínuo:**
  - Implementação de dashboards para monitoramento do desempenho e da disponibilidade.
- **Revisões e Auditorias:**
  - Revisões de código periódicas e auditorias de segurança.
- **Feedback e Melhorias:**
  - Coleta de feedback dos usuários e stakeholders.
  - Atualizações incrementais e refinamento das funcionalidades.
- **Documentação e Suporte:**
  - Atualização constante da documentação técnica e de usuário.
  - Treinamento e suporte para a equipe e os usuários finais.

---

## Fase 10: Lançamento e Pós-Lançamento
- **Validação Final:**
  - Revisão e validação dos critérios de aceitação.
- **Treinamento e Implantação:**
  - Treinamento dos usuários e implantação oficial do sistema.
- **Revisão de Lições Aprendidas:**
  - Coleta e análise de feedback para planejar futuras melhorias e novas funcionalidades (ex.: integrações com IA e expansão dos microsserviços).

---

> **Observação:** Este roadmap é um guia dinâmico e pode ser ajustado conforme o avanço do projeto e o feedback contínuo das equipes de desenvolvimento, design e stakeholders.

