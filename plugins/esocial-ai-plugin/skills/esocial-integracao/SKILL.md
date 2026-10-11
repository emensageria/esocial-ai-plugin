---
name: esocial-integracao
description: Projetar integrações seguras e auditáveis entre ERP, eSocial e eMensageria, incluindo operações, retries e segregação de contas e ambientes. Use em questões de arquitetura e implementação de API ou MCP.
---

# Arquitetura de integração eSocial

- Diferencie ambiente de `producao` e `producao-restrita`; nunca altere o ambiente implicitamente.
- Exija `codigo_conta` e `ambiente` em **cada ferramenta de negócio proposta**; valide autorização para a combinação identidade, conta, ambiente e permissão.
- Guarde credenciais no mecanismo seguro do cliente/servidor. Nunca apresente tokens ou certificados digitais nas respostas.
- Para transmissão e exclusão, adote confirmação humana prévia, logs auditáveis e mecanismos de idempotência.
- Nas operações assíncronas, acompanhe estados, retries com backoff e resultados, sem duplicar eventos inadvertidamente.
- Antes de recomendar ferramentas MCP, consulte `tools/list` na sessão autenticada; não invente nomes, atributos ou endpoints.
- Não presuma transporte ou mecanismo de autenticação sem documentação publicada **atualizada**. Consulte https://www.emensageria.com.br/ia-mcp/ .
- Separe requisitos futuros do comportamento confirmado de produção.