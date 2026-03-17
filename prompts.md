# 🧪 Engenharia de Prompts Estratégicos

Abaixo estão os prompts que utilizei no **NotebookLM** para construir este caderno temático e resolver problemas técnicos reais.

### 🔍 Análise de Diagnóstico
> **Prompt:** "Atue como um Especialista em Performance de Banco de Dados. Analise este Plano de Execução SQL [DADOS_DO_PLANO] e identifique operações de alto custo, como 'Table Access Full' em tabelas grandes. Sugira índices ou refatoração de código."

### ⚙️ Integração PowerShell + SQL
> **Prompt:** "Como posso garantir que o PowerShell envie parâmetros numéricos para o Oracle sem causar conversão implícita de tipos? Mostre como definir o OracleDbType.Int64 no script para não invalidar os índices do banco."

### 📝 Resumo de Documentação
> **Prompt:** "Com base no PDF da Documentação Oracle que fiz upload, resuma as 5 melhores práticas para criação de índices em colunas que recebem muitas funções de tratamento de texto (como UPPER e LOWER)."

### 🛡️ Prevenção de Erros (Troubleshooting)
> **Prompt:** "Liste os 3 maiores riscos de se reconstruir (REBUILD) um índice em um ambiente de produção durante o horário de pico e quais as alternativas mais seguras."
