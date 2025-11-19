# The docker composes used to run git.itsrye.dev

## Overview

This repository contains the Docker Compose files required to deploy the Gitea instance running at git.itsrye.dev.

## Preparation

To deploy this you need to first set up the env files and the secrets files.

## env files

- `./environment/cf.env`
- `./environment/db.env`
- `./environment/gitea.env`

## secrets files

- `/environment/secrets/db_password.txt`

Note: Ensure that the secrets directory is protected on your system (e.g., using `chmod 600` on the files).

## Deployment

To deploy the server just run:

```bash
docker compose up -d
```

The stack will start in the background and manage itself according to the configuration.

## Important Notes

Do *not* commit secrets to this repository.
The provided `.gitignore` rules help prevent accidental commits, but be mindful of this if you fork the project, however at that point, it becomes your responsibility.

The .gitignore files are configured as follows:

In the repository root:

```ignore
*.env
.env
```

and in the environment dir

```ignore
*.env
!.gitignore
!.gitkeep
```

and in the environment/secrets dir:

```ignore
*
!.gitignore
```