# Gym AI Agents

## Descrição do projeto
Este repositório reúne o trabalho prático do **Módulo 2** da Pós-graduação em **Data Analytics e Inteligência Artificial Aplicada a Negócios (FNAT)**.

O projeto propõe um atendimento escalável por e-mail para a MoveMais Academia, usando um ecossistema com **cinco agentes de IA especializados** (Vendas, Cancelamento, Renovação, Treinos e Nutrição), orquestrados no **n8n** e com suporte de **RAG** para respostas baseadas nos documentos da academia.

Neste repositório estão os principais entregáveis do case, como:
- fluxo do n8n exportado em JSON;
- prompts dos agentes;
- documentos de apoio da base de conhecimento.

## Breve descrição do case
No case, a MoveMais Academia (rede premium com três unidades na região metropolitana de Campinas) enfrenta aumento no volume de e-mails e diversidade de demandas de atendimento.

Para resolver o gargalo sem perder qualidade, a proposta é construir uma solução integrada com cinco agentes de IA que:
- classifiquem e roteiem mensagens por tipo de demanda;
- respondam com tom e escopo adequados a cada situação;
- usem RAG para consultar informações reais da academia (planos, protocolos de treino e guia nutricional);
- mantenham atenção a custo operacional e segurança da informação (incluindo cuidados com LGPD).

## Passo a passo para baixar o repositório e rodar a aplicação
1. **Clone o repositório**
   ```bash
   git clone https://github.com/abelfernando/Gym_AI_Agents.git
   cd Gym_AI_Agents
   ```

2. **Instale o Node.js 18+**
   - O n8n local depende de Node.js na versão 18 ou superior.

3. **Suba o n8n localmente**
   ```bash
   npx n8n
   ```
   - Acesse: `http://localhost:5678`

4. **Importe o workflow do projeto no n8n**
   - Use o arquivo: `Gym AI Agents.json`

5. **Configure as credenciais necessárias no n8n**
   - Gmail (OAuth)
   - Google Drive
   - OpenAI
   - Supabase

6. **Prepare a base de conhecimento para o RAG**
   - Garanta o uso dos documentos da pasta `Documentos`:
     - `Planos e Preços MoveMais.pdf`
     - `Protocolos de Treino MoveMais.pdf`
     - `Guia Nutricional MoveMais.pdf`

7. **Teste o fluxo de ponta a ponta**
   - Envie e-mails de teste para validar o roteamento entre os cinco agentes e as respostas geradas.
