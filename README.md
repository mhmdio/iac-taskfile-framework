# IaC Taskfile Framework

![taskfile](taskfile.png)

Taskfile <https://taskfile.dev/> that contains needed DevOps daily operations tasks and commands.

## Operations

- [AWS]()
  - `awscli`
  - `aws-vault`
- [Terraform]()
  - `terraform`
  - `tfsec`
  - `tflint`
  - `check`
  - `driftctl`
  - `tfenv`
- [Docker]()
  - `docker`
- [Helm]()
  - `helm`
  - `helmfile`
- [Ansible]()  
- [GitHub]()  
- [Terragrunt]()  
- [Kubernetes]()  
- [Brew]() (macOS)  
- [Chocolatey](https://chocolatey.org/) (windows)  
- [Scoop]() (windows)  
- [1password]()  
- [SteamPipe]()  

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
