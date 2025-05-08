# Desafio_Universidade_DIO
 sistema universitário, temos um modelo mais complexo devido à diversidade de interações. As entidades incluem Aluno, Curso, Disciplina, Professor e Avaliação.  Aluno: cadastrado em um ou mais cursos.


# 🎓 Banco de Dados - Universidade

Este projeto representa o modelo relacional de um sistema acadêmico universitário, com foco na gestão de alunos, cursos, professores, disciplinas e matrículas.

---

## 🧩 Modelo Relacional

### 1. `alunos`
| Campo        | Tipo        | PK | Not Null | Descrição               |
|--------------|-------------|----|----------|--------------------------|
| id_aluno     | INT         | ✅ | ✅       | Identificador do aluno   |
| nome         | VARCHAR(100)|    | ✅       | Nome completo do aluno   |
| data_nasc    | DATE        |    | ✅       | Data de nascimento       |
| cpf          | CHAR(11)    |    | ✅       | CPF do aluno             |
| email        | VARCHAR(100)|    |          | Email do aluno           |

---

### 2. `professores`
| Campo          | Tipo         | PK | Not Null | Descrição                  |
|----------------|--------------|----|----------|-----------------------------|
| id_professor   | INT          | ✅ | ✅       | Identificador do professor |
| nome           | VARCHAR(100) |    | ✅       | Nome do professor          |
| titulacao      | VARCHAR(50)  |    |          | Titulação acadêmica        |
| departamento_id| INT          |    | ✅       | FK para `departamentos`    |

---

### 3. `departamentos`
| Campo          | Tipo         | PK | Not Null | Descrição                      |
|----------------|--------------|----|----------|---------------------------------|
| id_departamento| INT          | ✅ | ✅       | Identificador do departamento  |
| nome           | VARCHAR(100) |    | ✅       | Nome do departamento           |

---

### 4. `cursos`
| Campo        | Tipo         | PK | Not Null | Descrição               |
|--------------|--------------|----|----------|--------------------------|
| id_curso     | INT          | ✅ | ✅       | Identificador do curso  |
| nome         | VARCHAR(100) |    | ✅       | Nome do curso           |
| duracao      | INT          |    | ✅       | Duração em semestres    |

---

### 5. `disciplinas`
| Campo         | Tipo         | PK | Not Null | Descrição                        |
|---------------|--------------|----|----------|-----------------------------------|
| id_disciplina | INT          | ✅ | ✅       | Identificador da disciplina       |
| nome          | VARCHAR(100) |    | ✅       | Nome da disciplina                |
| carga_horaria | INT          |    | ✅       | Carga horária da disciplina       |
| curso_id      | INT          |    | ✅       | FK para `cursos`                  |
| professor_id  | INT          |    | ✅       | FK para `professores`             |

---

### 6. `matriculas`
| Campo         | Tipo | PK | Not Null | Descrição                          |
|---------------|------|----|----------|-------------------------------------|
| id_matricula  | INT  | ✅ | ✅       | Identificador da matrícula         |
| aluno_id      | INT  |    | ✅       | FK para `alunos`                   |
| disciplina_id | INT  |    | ✅       | FK para `disciplinas`              |
| ano           | INT  |    | ✅       | Ano da matrícula                   |
| semestre      | INT  |    | ✅       | Semestre da matrícula (1 ou 2)     |

---

## 🔗 Relacionamentos

- `professores.departamento_id` → `departamentos.id_departamento`
- `disciplinas.professor_id` → `professores.id_professor`
- `disciplinas.curso_id` → `cursos.id_curso`
- `matriculas.aluno_id` → `alunos.id_aluno`
- `matriculas.disciplina_id` → `disciplinas.id_disciplina`

---

## 🛠️ Ferramentas Utilizadas

- MySQL Workbench para modelagem
- MySQL Server para execução e testes
- Markdown para documentação

---

# Criado: Amaury Prates
# Linkedin: https://www.linkedin.com/in/amaury-prates/

## 🧠 Observações

Este modelo pode ser expandido para incluir funcionalidades como controle de notas, histórico escolar, turmas, horários, entre outros.

