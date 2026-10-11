---
name: esocial-integracao
description: Projetar integrações ERP-eSocial-eMensageria com MCP remoto OAuth, separação por conta e ambiente, idempotência e auditoria.
---

# Arquitetura de integração eSocial

- MCP eMensageriaPro v2: `https://app.emensageria.com.br/esocial/mcp/v2/`, Streamable HTTP e OAuth. Não reutilize URLs nem autenticação antigas.
- Em **toda ferramenta de negócio**, envie `codigo_conta` e `ambiente`; aceite apenas `producao` e `producao-restrita`, sem ambiente padrão.
- Exija autorização server-side para identidade OAuth, conta, ambiente, vínculo ativo e operações permitidas no consentimento.
- Não exponha credenciais, certificados ou dados pessoais em logs, prompts, URLs e exemplos.
- Antes de transmissão, autorização de envio e exclusão, respeite a aprovação dentro da própria eMensageria.
- Adote idempotência, rastreabilidade de lotes/eventos e política de retentativas que evite reenvios duplicados.
- Antes de usar métodos MCP, consulte `tools/list` na conexão autenticada e respeite schemas reais.
- Em respostas do agente, separe hipótese de resultado de validação ou transmissão efetivamente confirmado.

Fontes: https://www.emensageria.com.br/ia-mcp/ e https://www.gov.br/esocial/pt-br/documentacao-tecnica .
