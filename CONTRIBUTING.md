# Guia de Contribuição e Padrões de Commit

Bem-vindo ao desenvolvimento do **UnBook 2.0**! Para manter a organização do projeto e facilitar o rastreamento de mudanças, adotamos o padrão de **Conventional Commits**.

---

## 🛠 Padrão de Commit

O formato de cada mensagem de commit deve seguir a seguinte estrutura:
`<tipo>(escopo opcional): <descrição curta>`

### Tipos Principais:

| Tipo | Descrição | Exemplo |
| :--- | :--- | :--- |
| **feat** | Uma nova funcionalidade | `feat(ui): adiciona widget do RU` |
| **fix** | Correção de um bug | `fix(auth): corrige erro no login @aluno` |
| **docs** | Alterações apenas na documentação | `docs: atualiza roadmap de desenvolvimento` |
| **style** | Mudanças de formatação/espaço (não afeta o código) | `style: formata identação do sitemap.md` |
| **refactor** | Refatoração de código que não muda funcionalidade | `refactor: otimiza query de busca de professores` |
| **chore** | Atualizações de build, pacotes ou infra | `chore: adiciona docker-compose inicial` |

---

## 📝 Exemplos de Mensagens

### Opção 1: Simples e Direta (Uso geral)
Ideal para mudanças rápidas e objetivas.
```text
docs: inicializa estrutura de documentação

```

### Opção 2: Detalhada (Corpo do commit)

Ideal para grandes adições ou alterações estruturais.

```text
docs: setup inicial da arquitetura do UnBook 2.0

- Adiciona PRD (Product Requirements Document)
- Adiciona Sitemap e Arquitetura de Informação
- Define estrutura de pastas para planejamento e design

```

---

## 💻 Como Realizar o seu Commit (Terminal)

Siga o fluxo abaixo para garantir que suas alterações sejam enviadas corretamente:

1. **Adicione os arquivos:**
```bash
git add .

```


2. **Crie o commit com a mensagem padronizada:**
```bash
git commit -m "tipo: descrição clara do que foi feito"

```

3. **Envie para o repositório remoto:**
```bash
git push origin main

```

---

## 💡 Dicas de Boas Práticas

* **Commits Atômicos:** Tente fazer commits pequenos que resolvam apenas uma coisa por vez.
* **Escopo:** Use o escopo (os parênteses) para indicar a área afetada, como `(ui)`, `(backend)`, `(scrapper)`.
* **Mensagens em Português:** Como o projeto é focado na comunidade da UnB, manteremos as descrições em português (PT-BR).
