# eSocial AI Plugin

Plugin público **não oficial** com cinco skills para orientação técnica do eSocial e integração opcional ao MCP eMensageriaPro.

## Skills

- [Documentação](skills/esocial-documentacao/SKILL.md)
- [Validação e revisão de XML](skills/esocial-xml/SKILL.md)
- [Diagnóstico de erros](skills/esocial-erros/SKILL.md)
- [Integração técnica](skills/esocial-integracao/SKILL.md)
- [MCP eMensageria](skills/esocial-mcp-emensageria/SKILL.md)

## MCP eMensageriaPro v2

- **URL:** `https://app.emensageria.com.br/esocial/mcp/v2/`
- **Transporte:** Streamable HTTP
- **Autenticação:** OAuth por login e consentimento na eMensageria
- **Campos em cada ferramenta de negócio:** `codigo_conta` e `ambiente` (`producao` ou `producao-restrita`)
- **Aprovações:** transmissões, autorizações de envio e exclusões requerem revisão e aprovação na eMensageria
- **Conexões:** https://app.emensageria.com.br/oauth/mcp/connections/

As URLs antigas foram desativadas. O consentimento restringe contas, ambientes e operações. Apenas contas com vínculo ativo ficam disponíveis, inclusive para administradores.

A instalação do plugin não concede automaticamente acesso ao MCP; o usuário deve concluir o OAuth no cliente compatível. Não coloque tokens, certificados, senhas ou dados pessoais em prompts.

## Documentos

- [Conexão MCP detalhada](references/mcp-emensageria.md)
- [Contrato de ferramentas](references/contrato-mcp-proposto.md)
- [Página oficial](https://www.emensageria.com.br/ia-mcp/)

Os nomes reais das ferramentas somente devem ser determinados após `tools/list` autenticado. A página oficial documenta a integração; não foi executado teste de autenticação real nesta publicação.

## Compatibilidade

Inclui manifesto portátil `plugin.json`, `mcp.json`, manifesto Claude `.claude-plugin/plugin.json` e skills `SKILL.md`. A validação final de carregamento depende da versão do cliente, e a publicação em diretórios oficiais exige revisão própria.
