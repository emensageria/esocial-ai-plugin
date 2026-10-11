# Contribuindo

Obrigado por contribuir com o eSocial AI Plugin.

- Faça uma issue ou PR contendo contexto, comportamento esperado e fontes públicas oficiais.
- Ao alterar orientações de eSocial, cite a URL oficial, versão do leiaute, nota técnica e data/vigência quando aplicáveis.
- Não adicione XMLs com CPF, CNPJ de clientes, salários, dados de saúde, números de recibos reais, certificados A1, senhas, tokens ou credenciais.
- Redija exemplos sintéticos. Não copie integralmente documentação oficial protegida; prefira links e sínteses.
- Separe fatos confirmados de hipóteses; não declare que o MCP tem uma ferramenta sem verificar `tools/list`.
- Toda orientação de operações sensíveis deve exigir verificação explícita da conta, ambiente e autorização.
- Evite dependências executáveis desnecessárias. Skills devem ser úteis mesmo sem o MCP.

## Verificação antes do PR

1. Verifique se cada skill possui `name` e `description` no YAML inicial.
2. Confirme que os diretórios declarados existem e os JSONs são válidos.
3. Rode `claude plugin validate ./plugins/esocial-ai-plugin` e `claude plugin validate .` quando o CLI estiver disponível.
4. Teste prompts com dados falsos e confirme que a skill não inventa regras, números de erro ou operações remotas.
