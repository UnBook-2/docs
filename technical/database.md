### Modelagem de Dados - UnBook 2.0

#### 1. Núcleo Acadêmico (Estrutura da UnB)

Precisamos separar a estrutura estática (Matérias) da estrutura dinâmica (Turmas/Ofertas).

**TB_DEPARTAMENTO**

* `id_departamento` (PK)
* `codigo` (ex: CIC, MAT, EST)
* `nome` (ex: Ciência da Computação)

**TB_MATERIA**

* `id_materia` (PK)
* `id_departamento` (FK)
* `codigo_materia` (ex: 113476)
* `nome`
* `ementa` (Texto longo)
* `creditos` (Inteiro - facilita cálculo de carga horária)
* `slug` (para URLs amigáveis: [unbook.com/materia/algoritmos](https://www.google.com/search?q=https://unbook.com/materia/algoritmos))

**TB_RELACAO_MATERIA** (Resolve Pré-requisitos/Co-requisitos de forma limpa)

* `id_relacao` (PK)
* `id_materia_origem` (FK)
* `id_materia_alvo` (FK)
* `tipo_relacao` (Enum: 'PRE_REQUISITO', 'CO_REQUISITO', 'EQUIVALENTE')

**TB_PROFESSOR**

* `id_professor` (PK)
* `id_departamento` (FK)
* `nome`
* `email_institucional`
* `foto_avatar` (URL)
* `status` (Ativo/Aposentado/Visitante)

---

#### 2. O Fluxo Temporal (Onde a aula acontece)

**TB_SEMESTRE**

* `id_semestre` (PK)
* `nome` (ex: "2026.1", "2025.2")
* `data_inicio`
* `data_fim`

**TB_TURMA** (A antiga "Professor/Matéria")

* `id_turma` (PK)
* `id_materia` (FK)
* `id_professor` (FK) — *Pode ser Null se a turma estiver "A definir"*
* `id_semestre` (FK) — *Crucial para histórico*
* `turma_letra` (ex: A, B, C)
* `horario_bruto` (String crua do MW: "24M12")
* `local`
* `vagas_ofertadas`
* `vagas_ocupadas`
* `taxa_trancamento` (Dado importado do relatório da UnB, se disponível)

---

#### 3. Usuários e Perfil (Social)

**TB_USUARIO**

* `id_usuario` (PK)
* `username` (Único)
* `email_institucional` (Para validação "@aluno.unb.br")
* `email_pessoal` (Para recuperação)
* `password_hash` (Nunca salvar senha pura, usar hash bcrypt/argon2)
* `curso`
* `matricula_hash` (Opcional: Hash da matrícula para evitar contas duplas, sem salvar o número real)
* `is_verificado` (Boolean: Confirmou o e-mail da UnB?)
* `avatar_id`
* `data_criacao`

---

#### 4. Avaliações e Métricas (O Coração do UnBook)

Aqui separamos os "dados da turma" da "opinião do aluno".

**TB_AVALIACAO**

* `id_avaliacao` (PK)
* `id_usuario` (FK)
* `id_turma` (FK) — *Liga ao Professor e Matéria automaticamente*
* `anonimo` (Boolean)
* `nota_geral` (1 a 5)
* `dificuldade` (1 a 5) — *Importante separar qualidade de dificuldade*
* `didatica` (1 a 5)
* `texto_comentario` (Opcional)
* `mencao_obtida` (Opcional: SS, MS, MM - ajuda a validar a nota)
* `data_avaliacao`

**TB_TAGS_AVALIACAO** (Tags pré-definidas para padronizar)

* `id_tag` (PK)
* `nome` (ex: "Cobra Presença", "Slides Ruins", "Prova Justa", "Leitura Pesada")
* `tipo` (Positivo/Negativo/Neutro)

**TB_AVALIACAO_TAGS_PIVOT** (Relacionamento N:N)

* `id_avaliacao` (FK)
* `id_tag` (FK)

**TB_INTERACAO_AVALIACAO** (Likes/Dislikes em comentários)

* `id_interacao` (PK)
* `id_avaliacao` (FK)
* `id_usuario` (FK)
* `tipo` (Upvote/Downvote/Report)
