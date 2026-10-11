# Contrato de ferramentas de negócio MCP eMensageria v2

O site oficial, atualizado em outubro de 2026, documenta que **cada ferramenta recebe `codigo_conta` e `ambiente`**; este documento explica o contrato esperado. Os schemas concretos ainda precisam de verificação em `tools/list` autenticado.

## Campos obrigatórios de cada ferramenta de negócio

```json
{
  "type": "object",
  "properties": {
    "codigo_conta": { "type": "string", "minLength": 1 },
    "ambiente": { "type": "string", "enum": ["producao", "producao-restrita"] }
  },
  "required": ["codigo_conta", "ambiente"]
}
```

Esse trecho é o **fragmento comum**, não o schema completo das ferramentas. Outros parâmetros (p. ex. lote ou evento) dependerão da implementação.

## Autorização e consentimento

- Autenticação via OAuth no endpoint único `https://app.emensageria.com.br/esocial/mcp/v2/`.
- Durante o consentimento, usuário escolhe contas, ambientes e operações; não há ambiente padrão.
- Validar server-side por chamada: identidade OAuth × `codigo_conta` × `ambiente` × permissão consentida × vínculo ativo.
- Negar recursos de outros tenants/ambientes, mesmo se o ID existir.
- Não enviar tokens OAuth, certificado PFX ou senhas em argumentos de ferramenta.
- Transmissões, autorizações de envio e exclusões devem seguir **aprovação na eMensageria**, antes da execução autorizada.
- Auditar mutações, proteger registros e aplicar idempotência para impedir duplicações acidentais.
- Não modificar métodos internos do MCP (`initialize`, `tools/list`, notificações).

## Cenários mínimos de teste

1. Campo `codigo_conta` ausente → validação rejeitada.
2. Campo `ambiente` ausente → validação rejeitada.
3. Ambiente inválido → validação rejeitada.
4. Token OAuth inválido/expirado → acesso negado.
5. Conta sem vínculo ativo → acesso negado, mesmo para administrador.
6. Conta ou ambiente fora do consentimento → acesso negado.
7. Operação fora das permissões → acesso negado.
8. Acesso cruzado a eventos/lotes de outro tenant → acesso negado.
9. Escrita sem aprovação necessária na eMensageria → negada.
10. Leitura autorizada → apenas os dados do escopo permitido.

Fontes: https://www.emensageria.com.br/ia-mcp/ (HTML fornecido em 11/10/2026).
