---
name: esocial-xml
description: Analisar estrutura de XML eSocial e orientar validação de XSD, namespaces, assinatura e regras de negócio. Use ao diagnosticar XML inválido ou preparar checagens técnicas.
---

# Revisão técnica de XML eSocial

1. Trabalhe somente com XML sintético ou anonimizado. Não peça certificados A1, senhas, tokens ou informações pessoais completas.
2. Determine evento, versão do leiaute e schema XSD oficial. Verifique a vigência e a estrutura do namespace.
3. Separe problemas de XML bem-formado, XSD, assinatura digital, identificação de evento e regras de negócio.
4. Indique erro observado, causa provável, fonte técnica, correção e teste de regressão sugerido.
5. Não afirme que ocorreu validação formal sem executar um validador XSD concreto sobre o documento com resultado verificável.
6. Revalide após alteração. Antes de qualquer ação remota, confirme autorização, `codigo_conta` e `ambiente`.

Referência: https://www.gov.br/esocial/pt-br/documentacao-tecnica .