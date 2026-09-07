# Backlog — Sistema de Gestão Acadêmica

(Gustavo Santos Moreira e Rafael Barbosa Candido).

**Capacidade estimada da equipe por sprint:** a definir
**DoD:** funcionalidade testada, sem regra de negócio quebrada, RBAC aplicado no backend

---

## Epics

| Tag | Epic | Descrição |
|---|---|---|
| EP.1 | Autenticação e Controle de Acesso | Login com JWT e RBAC via decorators por perfil, com checagem por recurso |
| EP.2 | Cadastro de Estudantes | Cadastro, edição e inativação de estudantes pela Coordenação |
| EP.3 | Cadastro de Professores | Cadastro, edição e inativação de professores pela Coordenação |
| EP.4 | Cursos e Disciplinas | CRUD de cursos e disciplinas, com bloqueio de exclusão quando houver vínculos ativos |
| EP.5 | Turmas e Matrículas | CRUD de turmas, vínculo de professores às turmas e matrícula de alunos |
| EP.6 | Lançamento de Notas e Cálculo de Média | Lançamento de notas pelo professor e cálculo automático de média via Template Method |
| EP.7 | Frequência | Lançamento e cálculo de percentual de frequência por disciplina |
| EP.8 | Boletim e Histórico Escolar | Consolidação do boletim do período corrente e do histórico permanente, com visibilidade por perfil |
| EP.9 | Dashboard Adaptativo | Painel inicial que se adapta ao perfil do usuário logado |

---

## Sprint 1 — MVP

Menor fluxo ponta a ponta: Coordenação monta uma turma, Professor lança nota e frequência, Aluno vê o boletim.

| Rank | Estimativa | Epic | User Story | Prioridade | Sprint |
|---|---|---|---|---|---|
| 1 | 3 | EP.1 | Como usuário do sistema, quero fazer login com minhas credenciais, para acessar apenas as funcionalidades do meu perfil (Coordenação, Professor ou Aluno). | Altíssima | 1 |
| 2 | 3 | EP.1 | Como Coordenação, quero que cada perfil só consiga ver e executar as ações liberadas para ele. | Altíssima | 1 |
| 3 | 2 | EP.2 | Como Coordenação, quero cadastrar um estudante com nome e curso vinculado, para poder matriculá-lo em uma turma. | Altíssima | 1 |
| 4 | 2 | EP.3 | Como Coordenação, quero cadastrar um professor com nome, para poder vinculá-lo a uma turma. | Altíssima | 1 |
| 5 | 2 | EP.4 | Como Coordenação, quero cadastrar um curso e uma disciplina, para ter o que oferecer em uma turma. | Altíssima | 1 |
| 6 | 3 | EP.5 | Como Coordenação, quero criar uma turma vinculada a uma disciplina e a um período letivo, vincular um professor a ela e matricular alunos. | Altíssima | 1 |
| 7 | 5 | EP.6 | Como Professor, quero lançar notas dos alunos na minha turma e ver a média calculada automaticamente, para registrar a avaliação sem calcular na mão. | Altíssima | 1 |
| 8 | 3 | EP.7 | Como Professor, quero lançar a frequência dos alunos na minha turma e ver o percentual calculado automaticamente. | Altíssima | 1 |
| 9 | 3 | EP.8 | Como Aluno, quero ver minha nota, média e frequência na turma em que estou matriculado. | Altíssima | 1 |
| 10 | 5 | EP.5 | Como Professor, quero só conseguir agir na turma em que estou de fato vinculado, para que minhas ações não afetem turmas de outros professores. | Altíssima | 1 |

---

## Sprint 2 — Fluxo robusto

Edição/inativação de cadastros, regras que evitam dados inconsistentes, cálculo de média por critério real da disciplina, boletim e histórico completos.

| Rank | Estimativa | Epic | User Story | Prioridade | Sprint |
|---|---|---|---|---|---|
| 11 | 2 | EP.2 | Como Coordenação, quero editar ou inativar um estudante, para manter a base atualizada sem apagar seu histórico. | Altíssima | 2 |
| 12 | 2 | EP.3 | Como Coordenação, quero editar ou inativar um professor, para manter a base atualizada sem apagar seus lançamentos anteriores. | Altíssima | 2 |
| 13 | 2 | EP.4 | Como Coordenação, quero ser impedida de excluir uma disciplina que já tenha turmas ativas ou notas lançadas. | Altíssima | 2 |
| 14 | 2 | EP.5 | Como Coordenação, quero ser impedida de matricular o mesmo aluno duas vezes na mesma turma. | Altíssima | 2 |
| 15 | 8 | EP.6 | Como Professor, quero que a média final leve em conta o critério de ponderação específico da minha disciplina. | Altíssima | 2 |
| 16 | 3 | EP.6 | Como Coordenação, quero que só seja possível lançar nota ou frequência em turmas ativas. | Alta | 2 |
| 17 | 5 | EP.8 | Como Aluno, quero ver meu boletim completo — todas as disciplinas do período, com nota, média, frequência e situação —, para saber exatamente como estou indo. | Altíssima | 2 |
| 18 | 3 | EP.8 | Como Coordenação, quero visualizar o boletim completo de qualquer aluno. | Altíssima | 2 |
| 19 | 2 | EP.8 | Como Professor, quero visualizar apenas a parte do boletim referente à minha própria disciplina/turma. | Alta | 2 |
| 20 | 5 | EP.8 | Como Aluno, quero visualizar meu histórico escolar consolidado de todos os períodos já cursados. | Altíssima | 2 |
| 21 | 2 | EP.8 | Como Coordenação, quero visualizar o histórico escolar de qualquer aluno, para consultas administrativas. | Alta | 2 |

---

## Sprint 3 — Dia a dia

Painéis de atalho e rastreabilidade administrativa.

| Rank | Estimativa | Epic | User Story | Prioridade | Sprint |
|---|---|---|---|---|---|
| 22 | 3 | EP.9 | Como Coordenação, quero ver no meu painel indicadores gerais (alunos ativos, turmas ativas, disciplinas ofertadas, professores ativos) e atalhos para os cadastros. | Alta | 3 |
| 23 | 2 | EP.9 | Como Professor, quero ver no meu painel as turmas em que estou vinculado no período corrente. | Alta | 3 |
| 24 | 2 | EP.9 | Como Aluno, quero ver no meu painel um resumo de notas e frequência do período corrente, com atalho para boletim e histórico. | Alta | 3 |
| 25 | 2 | EP.9 | Como Professor, quero ver no meu painel um resumo de avaliações que ainda não lancei. | Média | 3 |
| 26 | 3 | EP.6 | Como Coordenação, quero que cada nota/frequência mantenha o registro do professor que a lançou, mesmo após a turma ser encerrada ou o professor desvinculado. | Alta | 3 |
| 27 | 2 | EP.5 | Como Coordenação, quero que a tela de acompanhamento mostre apenas as turmas do período letivo vigente como "ativas". | Alta | 3 |
| 28 | 2 | EP.3 | Como Professor, quero visualizar a lista completa de alunos matriculados nas minhas turmas com dados de contato. | Média | 3 |

---
