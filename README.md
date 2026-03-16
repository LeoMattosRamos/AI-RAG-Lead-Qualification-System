# 🤖 Sistema inteligente de Atendimento e Qualificação de Leads com IA

Sistema de **automação de atendimento e qualificação de leads com Inteligência Artificial** para negócios que recebem contatos via **WhatsApp e Instagram**.

O projeto foi desenvolvido para resolver um problema comum em empresas de serviços: **perda de faturamento causada pela demora no atendimento de novos leads**.

---

# 📌 Problema

Muitos negócios recebem grande volume de contatos diariamente através de:

- WhatsApp
- Instagram Direct

Porém enfrentam limitações operacionais como:

- Alto volume de mensagens simultâneas
- Contatos fora do horário comercial
- Equipe de atendimento limitada 
- Grande quantidade de curiosos ou leads pouco qualificados

Como consequência:

❌ Leads com real intenção de compra acabam **agendando com concorrentes que respondem primeiro**.

A velocidade de resposta é um dos fatores mais importantes na conversão de leads.

Na prática, isso gera:

- perda de faturamento
- baixa eficiência da equipe
- sobrecarga no atendimento humano
- falta de visibilidade sobre o funil de atendimento

---

# 💡 Solução

Desenvolvi um **sistema de atendimento inteligente automatizado com IA** que:

1. Centraliza os canais de atendimento  
2. Realiza **pré-atendimento automatizado e humanizado** 24/7
3. **Qualifica automaticamente os leads**  
4. Encaminha para humanos apenas leads com potencial de conversão  
5. Gera **dados estruturados e métricas de atendimento**

O objetivo é **aumentar a eficiência do atendimento e reduzir a perda de oportunidades de venda (faturamento)**, sem aumentar o número de funcionários.


---

# ⚙️ Fluxo do Sistema

Fluxo simplificado de funcionamento da solução:

```
Usuário entra em contato
(WhatsApp / Instagram)
         │
         ▼
Centralização das mensagens
(Plataforma de atendimento)
         │
         ▼
  Webhooks e Automação de workflow
        (N8N)
         │
         ▼
     Agente de IA
   (LLM — Gemini)
         │
         ▼
  Base de conhecimento
  (RAG + Hybrid Search)
         │
         ▼
  Qualificação do lead
      (automática)
         │
    ┌────┴────┐
    │         │
    ▼         ▼
Não qual.  Qualificado
    │         │
IA finaliza   Transfere
atendimento   p/ humano (com resumo estruturado)

               │
               ▼
        Atendimento
           humano
               │
               ▼
          Agendamento
               │
               ▼
        Registro de dados
               │
               ▼
      Dashboard de métricas
```

---

# 🧠 Funcionamento do sistema

## 1️⃣ Centralização de canais

Mensagens vindas de:

- WhatsApp
- Instagram

são centralizadas em uma única interface.

Benefícios:

- Histórico único de conversas
- Melhor organização do fluxo
- Atendimento mais eficiente

---

## 2️⃣ Pré-atendimento com IA

Um **agente de IA treinado com dados da clínica** inicia automaticamente o atendimento.

Características:

- Atendimento 24h por dia e 7 dias por semana
- Comunicação em linguagem natural e humanizada -> nada de chatbots robóticos
- Respostas contextualizadas
- Quebra de objeções
- Entendimento da intenção do usuário

Durante a conversa, o agente coleta informações importantes como:

- Interesse do paciente
- Tipo de procedimento
- Disponibilidade
- Dúvidas frequentes
- Objeções

---

## 3️⃣ Uso de RAG

Para garantir respostas mais precisas foi utilizado **RAG (Retrieval Augmented Generation)** com **Hybrid Search**.

A IA consulta uma base de conhecimento contendo:

- Procedimentos
- Profissionais
- Preços
- Horários
- Dúvidas frequentes
- Políticas da clínica

Isso reduz:

- Alucinações da IA
- Respostas inconsistentes
- Erros de informação

---

## 4️⃣ Qualificação automática de leads

Durante a conversa o sistema identifica se o contato possui **potencial de conversão**.

Critérios analisados:

- Interesse real no procedimento
- Intenção de agendamento
- Compatibilidade com os serviços da clínica

Quando um lead é qualificado:

➡️ o atendimento é transferido para um humano.

---

## 5️⃣ Transição IA → Humano

Antes de transferir o atendimento, o sistema gera um **resumo estruturado da conversa**, contendo:

- Nome do lead
- Interesse principal
- Dúvidas levantadas
- Intenção de agendamento
- Disponibilidade/preferência de horário
- Ação necessária que o humano deve tomar

Isso permite que o atendente humano continue o atendimento **sem reiniciar o processo**, de forma rápida e eficiente.

---

# 🗄️ Arquitetura de Dados

Para permitir análise de desempenho e tomada de decisão baseada em dados, o sistema registra eventos do atendimento em um **banco de dados estruturado**.

Os dados são organizados de forma otimizada para análises e geração de métricas operacionais.

Principais tipos de dados armazenados:

- Leads recebidos
- Informações coletadas durante o pré-atendimento
- Status de qualificação do lead
- Transferências para atendimento humano
- Agendamentos realizados
- Canal de origem do contato
- Timestamps de cada etapa do atendimento

Essa estrutura permite construir análises como:

- Volume de leads ao longo do tempo
- Taxa de qualificação
- Taxa de conversão para agendamento
- Tempo médio de atendimento
- Desempenho por canal de origem (WhatsApp vs Instagram)
- Entre outras métricas

O modelo de dados foi projetado para facilitar **consultas analíticas em SQL**, possibilitando a criação de dashboards e análises operacionais.

# 📊 Dashboard de métricas

O sistema também gera um **dashboard analítico de atendimento**.

Principais métricas:

- Total de leads recebidos
- Leads qualificados
- Agendamentos realizados
- Taxa de conversão
- Funil de atendimento
- Origem dos leads
- Evolução temporal dos atendimentos
- Mapa de calor dos dias/horários de atendimentos

Essas informações permitem gestão do fluxo de atendimento e **tomada de decisão baseada em dados**.

---

# 🧰 Tecnologias utilizadas

### Dados

- Postgres
- SQL

### Interface atendimento

- Centralização atendimento whatsapp + instagram em único local

### Inteligência Artificial

- LLMs (Gemini)
- RAG (Retrieval Augmented Generation)
- Hybrid Search

### Automação

- N8N

### Deploy e visualização

- GitHub
- Vercel

---

# 🔒 Nota sobre implementação

Por se tratar de um sistema utilizado em projetos reais, os **workflows completos de automação não estão públicos neste repositório**.

O objetivo deste projeto é demonstrar:

- A arquitetura da solução
- O problema de negócio resolvido
- O uso de IA com RAG
- A estratégia de qualificação de leads
- A estrutura de métricas e analytics

Detalhes específicos de implementação foram omitidos.

---

# 🚀 Benefícios da solução

✔ Atendimento 24h  
✔ Redução de leads perdidos  
✔ Aumento da taxa de conversão sem aumentar custo com funcionários  
✔ Maior eficiência da equipe de atendimento  
✔ Qualificação automática de contatos  
✔ Visibilidade completa do funil de atendimento  

---

# 📌 Objetivo do projeto

Demonstrar na prática como **Estratégia + Tecnologia + IA** podem ser utilizadas para gerar resultados reais ao negócio: **aumento de conversão e faturamento com sistema eficiente de atendimento**.
