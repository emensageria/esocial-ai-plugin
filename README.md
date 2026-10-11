# eSocial AI Plugin

Plugin comunitário e **não oficial** para análise técnica do eSocial brasileiro por agentes de IA. Inclui skills de documentação, revisão de XML, diagnóstico de retornos e integração, além de instruções para conexão **opcional** ao MCP remoto da [eMensageriaPro](https://www.emensageria.com.br/ia-mcp/).

> **Status:** versão inicial (0.1.0). Não é um produto do Governo Federal; não substitui XSD oficial, validação do eSocial, assessoria técnica ou jurídica. Nenhum evento é transmitido pelas skills.

## Conteúdo

| Skill | Função |
| --- | --- |
| `esocial-documentacao` | Pesquisar documentação oficial, eventos, regras e vigência |
| `esocial-xml` | Revisar XML, identificar problemas e orientar validação XSD |
| `esocial-erros` | Interpretar erros, rejeições, recibos e próximos passos |
| `esocial-integracao` | Projetar integrações resilientes, seguras e auditáveis |
| `esocial-mcp-emensageria` | Orientar configuração e uso seguro do MCP eMensageria |

Todas as skills ficam em [`plugins/esocial-ai-plugin/skills/`](plugins/esocial-ai-plugin/skills/). Consulte o [README do plugin](plugins/esocial-ai-plugin/README.md).

## Instalação no Claude Code

No Claude Code (comandos **dentro** da sessão interativa):

```text
/plugin marketplace add marcelomdevasconcellos/esocial-ai-plugin
/plugin install esocial-ai-plugin@esocial-ai
```

A instalação do plugin **não autentica** automaticamente o MCP da eMensageria.

## Instalação no ChatGPT / Codex

O diretório `plugins/esocial-ai-plugin` contém o manifesto portátil `plugin.json` e skills `SKILL.md`. Ele pode ser empacotado em ZIP e submetido para revisão no diretório OpenAI. **Publicação no GitHub não significa aprovação ou instalação no ChatGPT**. Ver [documentação de plugins OpenAI](https://developers.openai.com/plugins/build/plugins).

## MCP eMensageria (opcional)

A documentação pública descreve um MCP remoto autenticado por Bearer Token, com endpoint específico por conta e ambiente:

```text
https://app.emensageria.com.br/esocial/mcp/<subdominio>/<ambiente>/
```

É preciso configurar a conexão autorizada separadamente. O endpoint único `/esocial/mcp/v2/` **é apenas uma proposta futura**; o repositório não declara nem anuncia esse endereço como ativo. Leia [MCP eMensageria](plugins/esocial-ai-plugin/references/mcp-emensageria.md).

**Contrato desejado para a próxima versão do MCP:** cada *ferramenta de negócio* deverá exigir explicitamente `codigo_conta` e `ambiente` (`producao` ou `producao-restrita`), com autorização efetiva no servidor. O plugin não modifica o backend automaticamente.

## Fontes oficiais

- [Documentação técnica eSocial](https://www.gov.br/esocial/pt-br/documentacao-tecnica)
- [Portal eSocial](https://www.gov.br/esocial/pt-br)
- [Agent Skills](https://agentskills.io/specification)

## Privacidade e segurança

Nunca inclua certificados digitais, senhas, tokens, chaves privadas ou dados reais de trabalhadores em issues, exemplos e prompts públicos. Anonimize XML e retornos. Consulte [Contribuindo](CONTRIBUTING.md).

## Licença

MIT — veja [LICENSE](LICENSE). O nome eSocial é utilizado apenas para identificar o domínio técnico; não há afiliação com o Governo Federal.
