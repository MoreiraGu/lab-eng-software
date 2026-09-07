# Decisões do Projeto

## 1. Stack Tecnológica

| Camada | Tecnologia |
|---|---|
| Frontend | React |
| Backend | FastAPI |
| ORM | SQLAlchemy |
| Banco de Dados | PostgreSQL |

---

## 2. Git Flow

Estratégia de branches adotada:

- **main** — código em produção, estável
- **develop** — branch de integração, código pronto para próxima release
- **feature/\<nome-da-feature\>** — desenvolvimento de novas funcionalidades, a partir de `develop`
- **release/\<versão\>** — preparação de uma nova versão (ajustes finais, testes)
- **hotfix/\<nome\>** — correções urgentes direto a partir de `main`

**Convenção de commits: [Conventional Commits](https://www.conventionalcommits.org/)**

Formato: `<tipo>(<escopo opcional>): <descrição>`

| Tipo | Uso |
|---|---|
| `feat` | Nova funcionalidade |
| `fix` | Correção de bug |
| `docs` | Alterações em documentação |
| `style` | Formatação, sem mudança de lógica (espaços, ponto e vírgula, etc.) |
| `refactor` | Refatoração sem alterar comportamento |
| `perf` | Melhoria de performance |
| `test` | Criação ou ajuste de testes |
| `chore` | Tarefas de manutenção (configs, dependências, build) |
| `ci` | Alterações em pipelines de CI/CD |
| `revert` | Reversão de um commit anterior |

**Exemplos:**
```
feat(auth): adiciona login via JWT
fix(api): corrige validação de e-mail no cadastro
docs(readme): atualiza instruções de instalação
chore(deps): atualiza versão do SQLAlchemy
```

- Breaking changes devem ser indicados com `!` após o tipo/escopo (ex: `feat!: altera estrutura de resposta da API`) ou com rodapé `BREAKING CHANGE:` no corpo do commit.
- Recomenda-se usar essa convenção para gerar changelog automático (ex: `standard-version`, `semantic-release`).

**Regras de PR:**
- [ ] Exigir revisão de pelo menos 1 pessoa
- [ ] Rodar testes automatizados antes do merge
- [ ] Squash ou merge commit? (definir)

---

## 3. Contrato de API

- Documentação via **OpenAPI/Swagger** (gerado automaticamente pelo FastAPI em `/docs`)
- Padrão de resposta (envelope, códigos HTTP, tratamento de erros)
- Versionamento da API (ex: `/api/v1/...`)
- Autenticação/Autorização (JWT, OAuth2, etc.)

**Template de endpoint:**

```
Método: 
Rota: 
Descrição: 
Request Body: 
Response: 
Códigos de erro: 
```

---

## 4. Figma

- Link do projeto: sem link ainda
- Design system / componentes reutilizáveis
- Fluxos de tela mapeados
- Responsável pela atualização do protótipo

---

## 5. DER (Diagrama Entidade-Relacionamento)

- Ferramenta utilizada: dbdiagram.io
- Link/arquivo do DER: sem link ainda
- Principais entidades: (listar dps quando tiver)
- Regras de negócio relevantes ao modelo de dados

---

## 6. Gestão de Tasks / Jira

- Board: `[link do Jira]`
- Fluxo de status das tasks:

```
Backlog → To Do → Em Progresso → Em Revisão → Concluído
```

- Padrão de nomenclatura de tasks (ex: `[FEATURE] Login de usuário`)
- Critérios de aceite obrigatórios em cada task
- Sprints: duração de `[X]` semanas

---

