# eSocial AI Plugin

Plugin público **não oficial** com skills para agentes de IA que trabalham com eventos e XML do eSocial brasileiro. Contém instruções independentes de qualquer serviço, além de uma skill de integração **opcional** ao MCP da eMensageriaPro.

## Skills incluídas

| Skill | Uso |
| --- | --- |
| [esocial-documentacao](skills/esocial-documentacao/SKILL.md) | Consulta de leiautes, regras e notas técnicas com fontes e vigência |
| [esocial-xml](skills/esocial-xml/SKILL.md) | Diagnóstico de XML, estrutura, namespace e validação XSD |
| [esocial-erros](skills/esocial-erros/SKILL.md) | Tratamento de retornos, rejeições, protocolos e retentativas |
| [esocial-integracao](skills/esocial-integracao/SKILL.md) | Boas práticas para integração eSocial: segurança, idempotência e auditoria |
| [esocial-mcp-emensageria](skills/esocial-mcp-emensageria/SKILL.md) | Configuração e operação segura do MCP remoto eMensageria |

## MCP remoto eMensageria

**Documentação oficial e atualizada:** https://www.emensageria.com.br/ia-mcp/

O endereço do servidor MCP e o método de autenticação da eMensageria foram alterados em outubro de 2026. Por isso, esta versão **não fixa** URL de endpoint nem mecanismo de autenticação. Consulte a página oficial ao conectar o cliente de IA e use os dados fornecidos no próprio sistema eMensageria. **Não copie configurações antigas.**

A instalação destas skills não cria uma conexão MCP nem fornece acesso a dados privados. Nomes e schemas de ferramentas somente podem ser conhecidos mediante conexão autorizada e descoberta `tools/list`.

A exigência de `codigo_conta` e `ambiente` para todas as ferramentas de negócio faz parte de um [contrato recomendado](references/contrato-mcp-proposto.md), devendo ser confirmada no backend atual antes de qualquer instrução de execução.

## Compatibilidade

O pacote contém o manifesto portátil `plugin.json`, skills no padrão Agent Skills e o manifesto do Claude Code em `.claude-plugin/plugin.json`. A configuração remota de MCP será incorporada a `mcp.json` **somente depois da confirmação verificável do novo endpoint e autenticação**. Publicar no GitHub não implica aprovação no diretório de plugins do ChatGPT.

## Segurança

- Não registre tokens, certificados A1, senhas ou dados pessoais de trabalhadores no GitHub ou no chat.
- Antes de transmitir, excluir ou retificar eventos, confirme a conta, o ambiente e o impacto da operação com o operador.
- Nunca afirme que um XML passou na validação XSD ou que um evento foi enviado sem resultado real.
- Confira a documentação oficial, versão, notas técnicas e vigência.

Veja também o [README raiz](../../README.md).