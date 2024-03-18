# [Ansible role terraform_agent](#terraform_agent)

Install and configure Terraform Agent (for TFC or TFE) on your system.

|GitHub|GitLab|Downloads|Version|
|------|------|---------|-------|
|[![github](https://github.com/robertdebock/ansible-role-terraform_agent/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-terraform_agent/actions)|[![gitlab](https://gitlab.com/robertdebock-iac/ansible-role-terraform_agent/badges/master/pipeline.svg)](https://gitlab.com/robertdebock-iac/ansible-role-terraform_agent)|[![downloads](https://img.shields.io/ansible/role/d/robertdebock/terraform_agent)](https://galaxy.ansible.com/robertdebock/terraform_agent)|[![Version](https://img.shields.io/github/release/robertdebock/ansible-role-terraform_agent.svg)](https://github.com/robertdebock/ansible-role-terraform_agent/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/robertdebock/ansible-role-terraform_agent/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: true

  roles:
    - role: robertdebock.terraform_agent
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/robertdebock/ansible-role-terraform_agent/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  become: true
  gather_facts: false

  roles:
    - role: robertdebock.bootstrap
    - role: robertdebock.ca_certificates
```

Also see a [full explanation and example](https://robertdebock.nl/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/robertdebock/ansible-role-terraform_agent/blob/master/defaults/main.yml):

```yaml
---
# defaults file for terraform_agent

# The version of the terraform_agent to install.
terraform_agent_version: "1.14.5"

# Where to install the terraform_agent.
terraform_agent_installation_path: /opt/tfc_agent

# The URL here Terraform Enterprise or Terraform Cloud is hosted.
terraform_agent_terraform_enterprise_address: "https://app.terraform.io"

# The Agent Token generated on Terraform Enterprise or Terraform Cloud.
# When no token (`""``) is defined, the agent will not be started.
terraform_agent_token: ""

# The name of the Agent as it will be registered as in Terraform Enterprise or Terraform Cloud.
terraform_agent_name: "my_agent"

# The log level of the agent. Either "TRACE", "DEBUG", "INFO", "WARN", or "ERROR".
terraform_agent_log_level: "INFO"
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/robertdebock/ansible-role-terraform_agent/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[robertdebock.bootstrap](https://galaxy.ansible.com/robertdebock/bootstrap)|[![Build Status GitHub](https://github.com/robertdebock/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-bootstrap/actions)|[![Build Status GitLab](https://gitlab.com/robertdebock-iac/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/robertdebock-iac/ansible-role-bootstrap)|
|[robertdebock.ca_certificates](https://galaxy.ansible.com/robertdebock/ca_certificates)|[![Build Status GitHub](https://github.com/robertdebock/ansible-role-ca_certificates/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-ca_certificates/actions)|[![Build Status GitLab](https://gitlab.com/robertdebock-iac/ansible-role-ca_certificates/badges/master/pipeline.svg)](https://gitlab.com/robertdebock-iac/ansible-role-ca_certificates)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/ansible-role-terraform_agent/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/robertdebock):

|container|tags|
|---------|----|
|[Amazon](https://hub.docker.com/r/robertdebock/amazonlinux)|Candidate|
|[Debian](https://hub.docker.com/r/robertdebock/debian)|all|
|[EL](https://hub.docker.com/r/robertdebock/enterpriselinux)|all|
|[Fedora](https://hub.docker.com/r/robertdebock/fedora)|all|
|[opensuse](https://hub.docker.com/r/robertdebock/opensuse)|all|
|[Ubuntu](https://hub.docker.com/r/robertdebock/ubuntu)|all|

The minimum version of Ansible required is 2.12, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/robertdebock/ansible-role-terraform_agent/issues).

## [License](#license)

[Apache-2.0](https://github.com/robertdebock/ansible-role-terraform_agent/blob/master/LICENSE).

## [Author Information](#author-information)

[robertdebock](https://robertdebock.nl/)

Please consider [sponsoring me](https://github.com/sponsors/robertdebock).
