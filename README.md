# IaC Taskfile Framework

![taskfile](taskfile.png)

Taskfile <https://taskfile.dev/> that contains needed DevOps daily operations tasks and commands.

## Operations

- [AWS]()
  - `awscli`
  - `aws-vault`
- [Terraform]()
  - `terraform`
- [Docker]()
  - `docker`
- [Helm]()
  - `helm`
  - `helmfile`
- [GitHub]()  - SOON!
  - `gh`
- [Terragrunt]()  - SOON!
  - `terragrunt`
- [Kubernetes]()  - SOON!
  - `kubectl`
- [Brew]() (macOS)  - SOON!
  - `brew`
- [Chocolatey](https://chocolatey.org/) (windows)  - SOON!
  - `choco`
- [1password]()  - SOON!
  - `1password`
- [SteamPipe]()  - SOON!
  - `steampipe`

## How to use

### git submodules

add `submodule` for the repo in `tasks` folder in your repo.

```bash
git submodule add https://github.com/mhmdio/iac-taskfile-framework tasks
```

update your `Taskfile.yml` to include the task files form `tasks` folder

```yml
includes:
  aws: ./tasks/aws
  docker: ./tasks/docker
  terraform: ./tasks/terraform
```

## Sample Taskfile

```yml
# https://taskfile.dev

version: '3'
dotenv: ['.env']
output: prefixed
vars:
env:

includes:
  aws: ./tasks/aws
  docker: ./tasks/docker
  terraform: ./tasks/terraform

tasks:

  default:
    desc: Hello MSG.
    cmds:
      - echo "{{.GREETING}}"
    silent: true

```
