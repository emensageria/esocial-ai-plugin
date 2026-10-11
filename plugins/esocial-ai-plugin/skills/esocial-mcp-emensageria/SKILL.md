---
name: esocial-mcp-emensageria
description: Configurar e utilizar com segurança o MCP remoto da eMensageriaPro em Claude, ChatGPT ou Codex. Use quando o usuário pedir conexão, autenticação, descoberta de ferramentas ou operações em conta/ambiente eSocial.
---

# Conexão ao MCP eMensageriaPro

1. Use **sempre** a documentação atualizada em https://www.emensageria.com.br/ia-mcp/ como referência para endpoint, transporte e autenticação.
2. **Atenção:** em outubro de 2026 o responsável informou que tanto a URL MCP quanto a autenticação foram alteradas. Não utilize configurações históricas armazenadas em caches, respostas anteriores ou exemplos antigos. Se o conteúdo atual não estiver acessível, explique a limitação em vez de inventar valores.
3. Oriente o usuário a inserir segredos somente na conexão segura do cliente, nunca no chat nem em repositórios públicos.
4. Após conexão autorizada, descubra a lista efetiva de ferramentas, seus schemas e permissões por `tools/list`. Não invente operações disponíveis.
5. Ao executar ferramenta de negócio, verifique se o schema atual exige `codigo_conta` e `ambiente`; no contrato-alvo do projeto, **ambos devem ser obrigatórios em todas as ferramentas de negócio** e validados pelo servidor. Não confunda contrato desejado com funcionalidade já publicada.
6. Diante de operação de escrita (transmissão, retificação, exclusão), confirme previamente conta, ambiente, evento, consequência e autorização.
7. Não afirme que uma operação foi executada sem resposta efetiva da ferramenta.

Referência adicional: [MCP eMensageria](../../references/mcp-emensageria.md).