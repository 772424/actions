# 772424 Reusable actions

## Usage

### Branch deploy

```yml
name: deploy

on:
  push:
    branches:
      - "master"

jobs:
  deploy:
    uses: 772424/actions/.github/workflows/deploy-current-branch.yml@main
    with:
      environment: preproduction
      deploy_path: /var/www/preprod.monsite.com
    secrets: inherit

```

### Tag release deploy

```yml
name: deploy

on:
  push:
    tags:
      - 'production/*'

jobs:
  deploy:
    uses: 772424/actions/.github/workflows/deploy-tagged-release.yml@main
    with:
      environment: production
      deploy_path: /var/www/monsite.com
    secrets: inherit
```
