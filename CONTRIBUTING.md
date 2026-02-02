# Padrão de Commit (Conventional Commits)

O formato deve ser: `<tipo>(escopo opcional): <descrição curta>`

**Tipos principais:**

* **feat:** Uma nova funcionalidade (ex: `feat(ui): adiciona widget do RU`).
* **fix:** Correção de um bug.
* **docs:** Alterações apenas na documentação (é o que você usará agora).
* **style:** Alterações que não afetam o sentido do código (espaços, formatação, etc).
* **refactor:** Alteração no código que não corrige bug nem adiciona funcionalidade.
* **chore:** Atualizações de tarefas de build, pacotes, etc.

---

# Exemplos de commits

Abaixo se encontram modelos de commits para se basear

### Opção A: Simples e Direta (Recomendada)

``` 
docs: inicializa estrutura de documentação 
```

### Opção B: Mais detalhada (Se for fazer via terminal)

```text
docs: setup inicial da arquitetura do UnBook 2.0

- Adiciona PRD (Product Requirements Document)
- Adiciona Sitemap e Arquitetura de Informação
- Define estrutura de pastas para planejamento e design

```

---

### Como fazer o commit (Comandos)

Se você estiver usando o terminal dentro da pasta do projeto:

```bash
# Adiciona todos os arquivos criados
git add .

# Faz o commit com a mensagem padronizada
git commit -m "docs: inicializa estrutura de documentação"

# Envia para o GitHub
git push origin main

```