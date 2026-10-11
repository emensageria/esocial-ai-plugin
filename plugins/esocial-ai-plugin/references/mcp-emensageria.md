# MCP remoto eMensageria — fonte viva

**Fonte canônica:** https://www.emensageria.com.br/ia-mcp/

> Aviso de atualização (11-10-2026): o proprietário confirmou alterações recentes no **endpoint MCP** e no **método de autenticação**. Ferramentas externas de busca podem apresentar conteúdo anterior em cache. Não utilizar, publicar ou inferir valores a partir de páginas indexadas antigas.

## Configuração recomendada

1. Consulte a página oficial em navegador com conteúdo atualizado ou a documentação disponibilizada pela plataforma autenticada.
2. Confirme a URL HTTPS efetiva do endpoint e o tipo atual de autenticação oferecido no cliente.
3. Insira credenciais apenas no fluxo oficial de conexão do cliente de IA. Não as envie como texto à conversa nem as insira em arquivos versionados.
4. Com a conexão autorizada, obtenha `tools/list` para descobrir nomes, descrições, permissões e schemas efetivos das ferramentas.
5. Faça primeiro testes de leitura e validação em ambiente de testes, com dados sintéticos.
6. Antes de operações de escrita, o operador deve conferir conta, ambiente, recurso de destino e efeito da operação.

## O que o plugin NÃO presume

- Não presume URL de endpoint atual ou versão do transporte.
- Não presume Bearer token, OAuth ou outro mecanismo enquanto a alteração recente não for confirmada em conteúdo atual.
- Não presume quais métodos estão disponíveis: a lista em `tools/list` é a fonte da sessão autenticada.
- Não presume que o MCP atualmente exige `codigo_conta` e `ambiente`; essa é uma política requerida para a evolução da interface.

## Contrato desejado para operações de negócio

Cada operação de negócio deverá receber dois argumentos **obrigatórios**:

- `codigo_conta`: string, código da conta/tenant.
- `ambiente`: enum `producao` ou `producao-restrita`.

O backend deve revalidar autorização em toda chamada, inclusive consultas. Isso não altera métodos internos do protocolo MCP, como `initialize` ou `tools/list`. Consulte [contrato proposto](contrato-mcp-proposto.md).