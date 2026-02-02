# Stack principal do projeto:

Em processo de decisão, porém como base pensamos nesse formato

## Arquitetura Técnica
* **Frontend:** Vue.js ou React (Mobile-First).
* **Backend:** Django (Python) - Robustez e facilidade com scripts.
* **Database:** PostgreSQL (Full Text Search).
* **ETL:** Django Management Commands + Celery para scraping.
* **Auth:** E-mail `@aluno.unb.br` apenas para validação (Hash), mantendo anonimato.