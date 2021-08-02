# IaC Taskfile Framework

![taskfile](taskfile.png)

Taskfile <https://taskfile.dev/> that contains needed DevOps daily operations tasks and commands.

## Operations

- [AWS](https://aws.amazon.com/)
  - `awscli`
  - `aws-vault`
- [Terraform](https://www.terraform.io/)
  - `terraform`
  - `tfsec`
  - `tflint`
  - `checkov`
  - `driftctl`
  - `tfenv`
- [Docker](https://www.docker.com/)
  - `docker`
- [Helm](https://helm.sh/)
  - `helm`
  - `helmfile`
- [Ansible](https://www.ansible.com/)  
- [GitHub](https://github.com/)  
- [Terragrunt](https://terragrunt.gruntwork.io/)  
- [Kubernetes](https://kubernetes.io/)  
- [Brew](https://brew.sh/) (macOS)  
- [Chocolatey](https://chocolatey.org/) (windows)  
- [Scoop](https://scoop.sh/) (windows)  
- [1password](https://1password.com/)  
- [SteamPipe](https://steampipe.io/)  

## How to use

### Install Taskfile

one command to install:

```bash
# For Installation To /usr/local/bin for user wide access with debug logging
# May require sudo sh
sh -c "$(curl --location https://taskfile.dev/install.sh)" -- -d -b /usr/local/bin
```

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

## Repos using IaC Taskfile framework

- <https://github.com/mhmdio/terraform-templates-base>