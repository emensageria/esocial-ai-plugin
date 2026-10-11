---
name: esocial-mcp-emensageria
description: Conectar e utilizar o MCP remoto eMensageriaPro v2 via Streamable HTTP e OAuth, com codigo_conta e ambiente obrigatórios em cada ferramenta de negócio.
---

# MCP eMensageriaPro v2

Use ao orientar configuração, consentimento, descoberta e execução de ferramentas eSocial via eMensageriaPro.

1. Endpoint oficial: `https://app.emensageria.com.br/esocial/mcp/v2/`. Transporte: **Streamable HTTP**. Autenticação: **OAuth** com login e consentimento na eMensageria. As URLs antigas foram desativadas; não sugira token Bearer manual.
2. Ao autorizar, selecione explicitamente contas, ambientes e operações; apenas contas com vínculo ativo podem ser utilizadas e nenhum ambiente é escolhido automaticamente.
3. Toda **ferramenta de negócio** deve receber explicitamente `codigo_conta` e `ambiente`, com `ambiente` igual a `producao` ou `producao-restrita`. Nunca infira esses argumentos nem reutilize contexto de chamadas anteriores sem confirmação.
4. Após conexão, descubra ferramentas reais e schemas por `tools/list`. Não invente nomes de ferramentas nem declare chamadas sem resultados.
5. Para transmissões, autorizações de envio e exclusões, indique que **é obrigatória revisão e aprovação na própria eMensageria**. Volte ao cliente para executar apenas a operação aprovada.
6. Não peça nem exiba tokens OAuth, senhas, códigos de autorização, PFX/Base64, certificados A1, chaves privadas ou dados sensíveis de trabalhadores. O cadastro de certificado ocorre apenas na interface oficial.
7. A revogação da conexão é feita em https://app.emensageria.com.br/oauth/mcp/connections/ .
8. Consulte https://www.emensageria.com.br/ia-mcp/ para alterações futuras. O site confirma o contrato público; ferramentas específicas precisam de autenticação para descoberta.

Consulte [referência de integração](../../references/mcp-emensageria.md).
