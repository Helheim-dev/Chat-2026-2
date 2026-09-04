# Guia de Contribuição

Este projeto utiliza **Turborepo** e **pnpm** para o gerenciamento de monorepo, integrando uma arquitetura híbrida de IA (**Mastra**), servidores **MCP**, uma interface em React e um backend em NestJS.

## 🛠️ Pré-requisitos
- **Node.js** (Versão 18 ou superior)
- **pnpm** (Gerenciador de pacotes padrão do monorepo)

## 🚀 Setup Inicial

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/fabrica-bayarea/Chat-2026-2.git
   cd Chat-2026-2
   ```

2. Copie as variáveis de ambiente: 
``` bash
cp .env.example .env
```

3. Instale as dependências na raiz:
   ```bash
   pnpm install
   ```

## Comandos Principais
- Rodar todo o ambiente em modo dev: pnpm dev

- Rodar apenas o Backend:
```bash
pnpm --filter backend dev
```

- Rodar apenas o Cérebro de IA (Mastra Core):
```bash
pnpm --filter mastra-core dev
```

- Rodar apenas o Servidor MCP:
```bash
pnpm --filter mcp-server dev
```

- Rodar apenas o Frontend:
```bash 
npm --filter web dev
```

- Adicionar dependência em um app especifico:
```bash
pnpm --filter <nome-do-app> add <pacote>
```

- Rodar build global:
```bash
pnpm build
```

- Executar linters e testes: pnpm lint / pnpm test

## 🌿 Git Workflow e Commits
**Adotamos uma variação simplificada e eficiente de Git Flow adaptada para o nosso monorepo:**

- **`main`**: 
  - Branch principal de produção e estabilidade. 
  - Código aqui é testado e pronto para deploy. 
  - **Nenhum commit direto é permitido.** Toda alteração entra via Pull Request revisado.

- **`develop`**: 
  - Branch de integração para a próxima release.
  - **Nenhum commit direto é permitido.** Toda alteração entra via Pull Request revisado.

- **Branchs de Funcionalidade (`feature/*`):**
   - **São estritamente temporárias:** Nascem para resolver uma tarefa específica e morrem logo após a conclusão.
  - Utilizada para desenvolver novas features, correções ou melhorias.
  - Devem ser criadas sempre a partir da `develop`.
  - *Exemplo:* 
  ```bash
  git checkout develop
  git checkout -b feature/mastra-core-mcp-integration
  ```

- **Branchs de Correção (`fix/*`):**
   - **São estritamente temporárias:** Nascem para resolver uma tarefa específica e morrem logo após a conclusão.
   - Utilizadas para correção de bugs rápidos.
   - Devem ser criadas sempre a partir da `develop`.
   - *Exemplo:* `git checkout -b fix/web-chat-overflow`

---

### O Ciclo de Vida e Limpeza das Branchs Temporárias
1. **Desenvolvimento:** Você programa, commita e abre o Pull Request a partir da sua branch temporária.
2. **Merge:** Após a aprovação, o código é integrado à `develop`.
3. **Exclusão Oritentada:** É **responsabilidade do desenvolvedor** deletar a branch temporária logo após o merge para evitar acúmulo de lixo no repositório remoto (muitas vezes usando o botão de exclusão automática da plataforma ou o comando local):

**Para apagar a branch localmente na sua máquina após o merge**

```bash
   git checkout develop
   git branch -d feature/sua-feature
```

---

### Utilizamos a convenção de Conventional Commits para padronizar o histórico do projeto:

- feature(web): novas funcionalidades na interface de chat.

- feature(backend): novas rotas ou lógicas na API NestJS.

- feature(mastra-core): novos agentes, fluxos ou ferramentas de IA.

- feature(mcp-server): novos endpoints ou conexões no servidor MCP.

- fix:, docs:, chore:, refactor: para correções, documentação e manutenção.

* Todos os PRs devem ser direcionados para a branch develop e passar pela aprovação dos Code Owners do respectivo escopo.

## 🔒 Boas Práticas de Segurança e IA

- Segredos e Credenciais: Nunca comite chaves de API, tokens de acesso ou senhas de banco de dados (.env). Utilize estritamente variáveis locais.

- Validação de Dados: Ao criar novas ferramentas de CRUD para o agente ou novas rotas no servidor MCP, garanta a tipagem estrita e validação dos dados (ex: utilizando Zod).

- Controle de Ações: Alterações sensíveis nos sistemas institucionais do IESB devem respeitar as diretrizes de RAG e governança definidas no escopo do projeto.

