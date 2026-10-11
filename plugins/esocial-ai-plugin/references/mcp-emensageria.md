# MCP eMensageriaPro v2 — configuração publicada

Fonte: HTML atualizado de https://www.emensageria.com.br/ia-mcp/ , fornecido em 11/10/2026.

## Conexão

- Endpoint HTTPS único: `https://app.emensageria.com.br/esocial/mcp/v2/`
- Transporte: **MCP Streamable HTTP**
- Autenticação: **OAuth**, com login e consentimento no sistema eMensageriaPro.
- No consentimento, o usuário seleciona **contas, ambientes e operações autorizadas**, sem ambiente automático.
- Apenas contas com vínculo ativo podem ser autorizadas, inclusive quando o usuário é administrador.
- URLs antigas baseadas em subdomínio e ambiente foram desativadas. Cadastre uma nova conexão OAuth; não use token manual da versão antiga.
- Gerenciamento/revogação: https://app.emensageria.com.br/oauth/mcp/connections/

## Argumentos obrigatórios por ferramenta de negócio

```json
{
  "codigo_conta": "empresa-exemplo",
  "ambiente": "producao-restrita"
}
```

`ambiente` admite somente `producao` e `producao-restrita`. O usuário deve informar ambos explicitamente em **cada ferramenta**; não inferir de chamadas anteriores. No backend, a autorização deve ser verificada com base em identidade OAuth, contas e ambientes consentidos, operação solicitada e vínculo ativo. Métodos internos do protocolo (`initialize`, `tools/list`) não recebem parâmetros de negócio.

## Operações sensíveis

A página descreve **revisão e aprovação na própria eMensageria** para transmissões, autorizações de envio e exclusões. Após a aprovação, o operador retorna ao cliente para executar a operação autorizada. Não confundir aprovação na IA com aprovação operacional na plataforma.

## Privacidade e segurança

Nunca solicite nem transmita senhas, tokens OAuth, refresh tokens, códigos de autorização, PFX/Base64, certificados A1 ou chaves privadas como argumentos de ferramenta ou texto do chat. O cadastro de certificados deve ocorrer na interface oficial eMensageria. Faça o login apenas no domínio oficial, minimize dados pessoais enviados a provedores de IA e proteja logs e armazenamento. Revogue conexões em caso de exposição.

## Descoberta de ferramentas

A documentação pública cita consulta de eventos, listagem de lotes, revisão/validação de XML e metadados. **Nomes precisos e schemas de tools ainda requerem `tools/list` numa sessão autorizada.** O HTML documenta o contrato de conexão, mas não prova que uma autenticação foi executada com sucesso.

## Compatibilidade

Há manifestos/configurações para clientes de plugins no repositório. Clientes ChatGPT, Claude, Codex e outros podem oferecer fluxos distintos de cadastro; use a URL única com OAuth no fluxo compatível com cada cliente. O instalador de skills por si só não concede acesso à conta.

Consulte também [Contrato das ferramentas](contrato-mcp-proposto.md).
