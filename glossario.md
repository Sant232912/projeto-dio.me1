# 📖 Glossário Técnico: Performance de Dados

| Termo | Definição Técnica |
| :--- | :--- |
| **Execution Plan** | O "mapa" que o banco de dados cria para decidir o caminho mais rápido para buscar os dados. |
| **Full Table Scan** | Ocorre quando o banco lê todas as linhas de uma tabela por falta de um índice adequado. |
| **Index Range Scan** | Uma busca eficiente onde o banco acessa apenas uma parte do índice para encontrar os dados. |
| **B-Tree Index** | O tipo mais comum de índice, organizado em árvore, ideal para buscas de alta seletividade. |
| **SARGability** | Capacidade de uma consulta SQL de utilizar os índices existentes (Search ARGumentable). |
| **Implicit Conversion** | Erro de performance onde o banco converte tipos de dados (ex: String para Number) em tempo real, invalidando índices. |
| **Tuning** | O processo de ajuste fino de queries ou parâmetros do servidor para melhorar a velocidade. |
| **Latência** | O tempo de atraso entre o pedido da informação e a entrega pelo banco de dados. |
