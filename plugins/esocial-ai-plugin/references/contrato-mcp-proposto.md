# Contrato MCP sugerido para eMensageria (não implantado por este plugin)

Esta seção descreve um **requisito do projeto**, não confirma o comportamento do servidor da eMensageria atualmente em produção.

## Parâmetros mandatórios em todas as ferramentas de negócio

```json
{
  "type": "object",
  "properties": {
    "codigo_conta": {
      "type": "string",
      "minLength": 1,
      "description": "Código da conta/tenant autorizado no servidor"
    },
    "ambiente": {
      "type": "string",
      "enum": ["producao", "producao-restrita"],
      "description": "Ambiente eSocial de execução"
    }
  },
  "required": ["codigo_conta", "ambiente"]
}
```

O contrato acima é **apenas a parte comum** a ser incorporada no `inputSchema` de cada ferramenta; uma ferramenta concreta incluirá os outros campos e obrigatoriedades.

## Regras de segurança

1. Vincule a credencial autenticada à identidade efetiva do usuário ou cliente.
2. Verifique server-side: `identidade × codigo_conta × ambiente × permissão` em **todas** as ferramentas de negócio.
3. Nunca faça fallback para conta padrão, último tenant ou ambiente de produção quando faltar argumento.
4. Negue acesso cruzado a dados de contas e ambientes diferentes, mesmo com IDs válidos de eventos/lotes.
5. Para transmissão, exclusão ou retificação: confirmação explícita, trilha de auditoria e chave de idempotência quando aplicável.
6. Use HTTPS, proteção de logs, segregação de dados e limites de taxa.
7. O esquema JSON não substitui controle de autorização no servidor.
8. Não modifique os métodos internos do protocolo MCP, tais como `initialize`, `notifications/initialized` e `tools/list`.

## Endpoint e autenticação

Use **apenas** a URL e o método de autenticação publicados atualmente em https://www.emensageria.com.br/ia-mcp/ . A URL e autenticação anteriores estão desatualizadas. Não criar `mcp.json` definitivo nem instruções de configuração de cliente até obter os novos valores confirmados.

## Testes mínimos

- Falta de `codigo_conta` → erro de validação.
- Falta de `ambiente` → erro de validação.
- Valor de `ambiente` fora do enum → erro de validação.
- Conta inexistente ou não autorizada → negação sem exposição de dados.
- Acesso a recurso de outro tenant/ambiente → negação.
- Operação de escrita sem autorização apropriada → negação.
- Chamada de consulta autorizada e válida → retorno somente do escopo correspondente.
- Repetição de operação mutável → comportamento idempotente quando pertinente.