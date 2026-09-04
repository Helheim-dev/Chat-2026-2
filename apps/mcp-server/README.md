# IESB MCP Server (`apps/mcp-server`)

Servidor customizado baseado no protocolo **MCP (Model Context Protocol)**. Sua principal função é conectar-se aos bancos de dados legados e sistemas externos do IESB e expor operações seguras de leitura e escrita (CRUD) para que os agentes de IA possam consumi-las.

## 🔌 Arquitetura e Protocolo

- Desenvolvido utilizando o SDK oficial `@modelcontextprotocol/sdk`.
- Expõe ferramentas (Tools) estritamente tipadas com validação de parâmetros.
- Utiliza transporte HTTP/SSE (ou Stdio para testes locais) para comunicação com os clientes (como o `apps/mastra-core`).

## ⚙️ Variáveis de Ambiente Necessárias

Para rodar o servidor, certifique-se de configurar as conexões com os bancos de dados do IESB no `.env`:
- `DB_HOST`
- `DB_PORT`
- `DB_USER`
- `DB_PASSWORD`
- `DB_NAME`

## 💻 Desenvolvimento Isolado

Para iniciar o servidor MCP em modo de desenvolvimento:
```bash
pnpm --filter mcp-server dev
```