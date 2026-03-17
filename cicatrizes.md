Cenário:
Eu precisava criar um script em PowerShell que consultasse o banco de dados Oracle para gerar um relatório diário de chamados críticos. O script funcionava perfeitamente em homologação (com poucos dados), mas em produção ele causava picos de CPU no servidor de banco de dados.

O Problema (A Dificuldade):
Ao usar o PowerShell para passar parâmetros para a query SQL, o script estava enviando as variáveis como strings simples, o que forçava o banco de dados a fazer uma conversão implícita de tipos (Implicit Data Conversion).

O que aconteceu: O banco de dados parava de usar o índice da coluna ID_CHAMADO (que é numérico) porque recebia uma string '12345'. Isso resultava em um Full Table Scan a cada execução do script.

A Engenharia de Prompts (O Troubleshooting):
Tentei resolver pedindo para a IA apenas "otimizar o script", mas a resposta foi genérica. Precisei refinar o prompt para encontrar a causa raiz:

Prompt Refinado: "IA, meu script PowerShell está executando uma query SQL no Oracle. A coluna ID é indexada (NUMBER), mas o Explain Plan mostra um 'TABLE ACCESS FULL'. Suspeito de conversão implícita. Como forço o PowerShell/ADO.NET a enviar o parâmetro como o tipo de dado correto (Int64) e não como String?"

A Solução Técnica:
A IA me ajudou a ajustar o objeto de comando no PowerShell, definindo explicitamente o OracleDbType.Int64.

$command.Parameters.Add("id", "12345") # Enviado como string, mata o índice

$param = New-Object Oracle.ManagedDataAccess.Client.OracleParameter("id", [Oracle.ManagedDataAccess.Client.OracleDbType]::Int64)
$param.Value = 12345
$command.Parameters.Add($param) # Agora o banco usa o INDEX RANGE SCAN
