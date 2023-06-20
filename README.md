<h1 align="center">Tech Challenge</h1>

How's the weather? Let me tell you! Join me in fetching data.

This repo houses code to query a weather API utilizing an enterprise
architecture monorepo. It includes microservices built on a PaaS with IaC for
streamlined development, testing, and deployment.

There are two services that are primary of concern. The first is Design System
located in `/services/design-system`. This is used design the UI of components
in isolation. The next is the AdminClient located in `/services/admin-client`.
This is a NextJS app that uses the UI components.

## Getting Started

For a turn-key development environment,
[fork the repo](https://github.com/aerisapp/tech-challenge/fork) and open in
Github Codespaces.

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/codespaces/new?hide_repo_select=true&ref=main&repo=438855397)

Alternatively, build, test, and deploy apps locally using the
[devcontainer](docs/devcontainer.md).

### Pull Request Lifecycle (~5 mins)

1. Checkout a new branch from main using git.

   ```bash
   git checkout -b feature/improve-readme
   ```

2. Work on changes (e.g. fix a bug or add a new feature). Build, lint, and unit
   test projects.

   ```bash
   rush build
   rush lint
   rush test
   ```

3. Stage and commit changes using
   [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/#specification).

   ```bash
   git add .
   git commit -m 'doc: fix spelling of computers'
   ```

4. (Optional) If changing a library that is published to NPM, document
   [semantic version](https://semver.org/) changes, generate Changelogs, and
   commit changes.

   ```bash
   rush change
   rush version --bump
   git commit -m 'chore: bump change log'
   ```

5. Push code and open a PR. Celebrate contributing.

   ```bash
   git push
   ```

## Documentation

See [Documentation](docs/index.md).

> **Note** Use `rush help` for information on builtin commands.
