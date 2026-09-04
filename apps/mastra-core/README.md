```markdown
# Mastra Core (`apps/mastra-core`)

Pacote responsável pelo cérebro de inteligência artificial do chatbot. Utiliza o framework **Mastra** para gerenciar o fluxo de conversação, os agentes especializados, as políticas de segurança via RAG e a conexão com os servidores MCP externos.

## 🧠 Arquitetura de IA

- **LLM Híbrido:** Suporte a provedores em nuvem (ex: OpenAI) e endpoints locais on-premise hospedados na infraestrutura do IESB (via Ollama/vLLM).
- **Ferramentas (Tools) via MCP:** Consumo dinâmico de ferramentas de CRUD expostas por servidores MCP externos (Secretaria, Financeiro, etc.).
- **Guardrails por RAG:** Validação prévia das normativas institucionais antes de autorizar alterações nos bancos de dados.

## ⚙️ Variáveis de Ambiente Necessárias

Certifique-se de configurar as seguintes variáveis no `.env` da raiz:
- `OPENAI_API_KEY` (Caso utilize nuvem)
- `LOCAL_LLM_BASE_URL` (Caso utilize endpoint local no IESB)
- URLs e tokens dos servidores MCP externos.

## 💻 Desenvolvimento Isolado

Para rodar apenas este pacote em desenvolvimento:
```bash
pnpm --filter mastra-core dev
```