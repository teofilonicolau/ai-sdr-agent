<div align="center">
  <a href="https://brightdata.com/">
    <img src="https://mintlify.s3.us-west-1.amazonaws.com/brightdata/logo/light.svg" width="300" alt="Bright Data Logo">
  </a>

# TamarAI SDR Agent

Prospecção em tempo real com inteligência multi-agente e personalização baseada em triggers.

<img src="https://img.shields.io/badge/python-3.11+-blue" />
<img src="https://img.shields.io/badge/OpenAI-API-blueviolet" />
<img src="https://img.shields.io/badge/License-MIT-blue" />
</div>

<div align="center">
<img src="https://media.brightdata.com/2025/09/AI-SDR-Agent-demo.gif" alt="Demonstração do Agente AI SDR/BDR">
</div>

---

## Visão Geral

Este sistema utiliza **5 agentes de IA especializados**:
  1. **Agente de Descoberta de Empresas** — Encontra empresas que correspondem ao seu ICP (Perfil de Cliente Ideal)
  2. **Agente de Detecção de Triggers** — Identifica sinais de compra e o momento ideal
  3. **Agente de Pesquisa de Contatos** — Extrai informações de tomadores de decisão
  4. **Agente de Geração de Mensagens** — Cria abordagens personalizadas
  5. **Gerente de Pipeline** — Pontua leads e integra com CRM

[**Visite o guia passo a passo no nosso blog**](https://brightdata.com/blog/ai/ai-sdr-agent-with-web-mcp)

---

## Pré-requisitos

- Python 3.11+
- Node.js e npm (para o servidor MCP)
- Chaves de API:
    - [Chave da API OpenAI](https://platform.openai.com/api-keys)
    - Conta [Bright Data](https://brightdata.com/) com acesso ao Web MCP
    - Credenciais do HubSpot CRM (opcional)

---

## Início Rápido

1. **Clone e configure:**

        git clone https://github.com/teofilonicolau/ai-sdr-agent.git
        cd ai-sdr-agent
        python setup.py

2. **Configure as chaves de API:**  
   Edite o arquivo `.env` com suas credenciais:

        OPENAI_API_KEY=sua_chave_aqui
        BRIGHT_DATA_API_TOKEN=seu_token_aqui
        HUBSPOT_API_KEY=sua_chave_hubspot_aqui

3. **Teste o sistema:**

        python test_workflow.py

4. **Execute a aplicação:**

        streamlit run ai_bdr_system.py

---

## Funcionalidades

- **Fluxo de Trabalho Multi-Agente:** Processamento paralelo, dados em tempo real, pontuação e integração com CRM
- **Inteligência de Triggers:** Picos de contratação, financiamento, mudanças de liderança, expansão
- **Motor de Personalização:** Sensível ao contexto, baseado em triggers, multi-canal, testes A/B
- **Exportação e Integração:** CSV, sincronização com HubSpot, mapeamento de campos, contatos em massa

---

## Arquitetura do Sistema

    ┌─────────────────────────────────────────────────────────────┐
    │                    Frontend Streamlit                       │
    ├─────────────────────────────────────────────────────────────┤
    │                    Orquestração CrewAI                      │
    ├─────────────────────────────────────────────────────────────┤
    │  Descoberta │ Triggers │ Contatos │ Mensagens │ Gerente     │
    │   Agente    │  Agente  │  Agente  │  Agente   │ de Pipeline │
    ├─────────────────────────────────────────────────────────────┤
    │    Bright Data MCP │ OpenAI │ HubSpot API                  │
    └─────────────────────────────────────────────────────────────┘

---

## Configuração

### Segmentação de ICP (Perfil de Cliente Ideal)
  - Seleção de Indústria (SaaS, FinTech, E-commerce, etc.)
  - Faixas de tamanho da empresa
  - Segmentação geográfica
  - Critérios personalizados

### Tipos de Mensagem
  - Campanhas de e-mail frio (Cold Email)
  - Solicitações de conexão no LinkedIn
  - Sequências de follow-up
  - Templates personalizados

### Pontuação de Leads (Lead Scoring)
  - Pontuação de correspondência de ICP (30%)
  - Pontuação de evento de trigger (30%)
  - Pontuação de qualidade do contato (20%)
  - Otimização de timing (20%)

---

## Integrações de API

### Bright Data MCP
  - Web scraping em tempo real
  - Dados de empresas do LinkedIn
  - Notícias e comunicados de imprensa
  - Informações de contato

### OpenAI GPT-4
  - Personalização de mensagens
  - Geração de conteúdo
  - Análise de triggers
  - Qualificação de leads

### HubSpot CRM
  - Criação/atualização de contatos
  - Sincronização de pontuação de leads
  - Propriedades personalizadas
  - Gerenciamento de pipeline

---

## Solução de Problemas

1. **Erros de Conexão MCP**

        npm install -g @brightdata/mcp

2. **Dependências Ausentes**

        pip install -r requirements.txt

3. **Erros de Chave de API**

    - Verifique as chaves no arquivo `.env`
    - Verifique as cotas e permissões da API

### Validação

        python test_workflow.py

---

## Métricas de Desempenho

- Empresas descobertas: 15-25
- Eventos de trigger: 8-15
- Contatos de qualidade: 40-60
- Taxa de resposta: 15-25%
- Agendamento de reuniões: 3-8%

---

## Segurança e Privacidade

- Chaves de API armazenadas em variáveis de ambiente
- Sem persistência de dados além da sessão
- Manuseio de contatos em conformidade com GDPR
- Limite de taxa (rate limiting) para proteção da API

---

## Licença

Este projeto é para fins educacionais e de demonstração interna.

---

## Saiba Mais

- [Como funciona o Web MCP da Bright Data](https://docs.brightdata.com/mcp-server/overview)
- [Documentação do Streamlit](https://docs.streamlit.io/)
- [Documentação da Plataforma OpenAI](https://platform.openai.com/docs)
- [Documentação do CrewAI](https://docs.crewai.com/)

---

**Desenvolvido por TamarAI | Powered by Bright Data & OpenAI**
