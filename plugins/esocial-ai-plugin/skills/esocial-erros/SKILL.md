---
name: esocial-erros
description: Interpretar erros de processamento, rejeições, respostas de lotes e recibos do eSocial. Use quando houver códigos de retorno ou mensagens de erro, sem inventar status ou protocolos.
---

# Diagnóstico de retornos e rejeições

1. Analise código, mensagem, origem e etapa da operação; use somente retornos sintéticos ou devidamente anonimizados.
2. Distinga erro de conexão, autenticação, XML/XSD, assinatura, regra de negócio, recepção, consulta e situação pendente.
3. Consulte documentação oficial para sustentar interpretações, indicando versão e data quando relevantes.
4. Apresente causas prováveis e passos verificáveis de correção.
5. Não recomende reenvio indiscriminado: avalie status anterior, duplicidades, recibos e idempotência.
6. Não declare sucesso, falha definitiva, recibo ou transmissão sem evidência real.
7. Para chamadas MCP, solicite confirmação da conta, ambiente e operação; ferramentas disponíveis devem ser descobertas em `tools/list`.

Fonte: https://www.gov.br/esocial/pt-br/documentacao-tecnica .