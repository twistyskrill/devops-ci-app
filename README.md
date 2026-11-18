# devops-ci-app

Учебное Flask-приложение для практической работы № 10.

CI: Pylint → pytest → Docker build → smoke-test → GHCR.

Публикация образа выполняется только из `main`. В Pull Request выполняются проверки без push.

- health endpoint: `/health`;
- образ: `ghcr.io/twistyskrill/devops-ci-app`;
- основной workflow: `.github/workflows/ci.yml`.

## Версионные выпуски и воспроизводимость

Push в main публикует полный SHA и latest. Git-тег v1.1.0 публикует Docker-тег 1.1.0, не меняя latest и ранее опубликованные SHA-теги. PR проверяется без публикации. В Push image сохраняется digest опубликованных тегов. Версионные теги повторно не назначаются другим коммитам.

Развёртывание готового образа описано в [docs/server-setup.md](docs/server-setup.md).
