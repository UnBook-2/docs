# Documento de Visão e Escopo: UnBook 2.0
**Versão:** 2.1 (Draft Inicial)
**Status:** Em Planejamento

## 1. Introdução
O UnBook 2.0 é um ecossistema completo de suporte à decisão de matrícula e compartilhamento de conhecimento para a comunidade da Universidade de Brasília (UnB). O foco muda da "avaliação da pessoa" para a "experiência de aprendizado", garantindo transparência e anonimato.

## 2. Pilares do Projeto
1.  **Experiência, não Aparência:** Foco na didática, cobrança e suporte, não na pessoa do professor.
2.  **Anonimato:** Garantia técnica e visual para feedbacks honestos e seguros.
3.  **Espaço Seguro:** Moderação híbrida (IA + Comunidade) para qualidade da informação.

## 3. Core Features (Funcionalidades Principais)

### 3.1. Montador de Grades ("Grade Builder") & CSP
* **Gerador Visual:** Interface drag-and-drop.
* **CSP (Constraint Satisfaction Problems):** Algoritmo matemático para gerar grades ideais baseadas em restrições (ex: "Manhãs livres").
* **Integração:** Dados reais raspados do SIGAA/Matrícula Web.
* **Alertas:** Detecção de choques e cálculo de carga horária.

### 3.2. Inteligência de Avaliação
* **Resumos via LLM:** "Prós", "Contras" e "Dica de Ouro" gerados automaticamente.
* **Análise de Sentimento:** Tags automáticas ("Cobrança Alta", "Didático").

### 3.3. Banco de Materiais (Contextual)
* **Anexos em Comentários:** Upload de provas e resumos vinculados à avaliação da matéria.
* **Filtros:** Busca por "Matérias Coxas" vs. "Conteudistas".

### 3.4. Rota de Fuga & Recomendação
* Filtros baseados em dados: Matérias para aumentar CR vs. Matérias para aprendizado profundo.

## 4. Soluções para Problemas Antigos
* **Cold Start:** Importar dados legados e fazer scraping de metadados (horários/ementas) para o site nascer útil.
* **Custo:** Uso de Cache (Redis) e LLMs menores/locais para reduzir custos de servidor e API.
* **Engajamento:** Gamificação (Badges, Ranking de contribuição) e utilidade diária (Cardápio RU).