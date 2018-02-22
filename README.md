# ansible-psql
psql configuration that I use as a Postgres DBA.

## Requirements
Mac OS >= 10
Ansible >= 2.0
Postgres >= 9.6

## Setup
Create local `ansible.cfg`

```
[defaults]
roles_path=../
retry_files_enabled = False
vault_password_file = <path_to_vault_file>
```

Create vault file to store username and password.

```
ansible-vault create psql_vault.yml
```

Add variables to vault:
```
---
pg_user: <username>
pg_pass: <password>
```

Run playbook

```
ansible-playbook psql_config.yml
```


## Inspired By
http://www.craigkerstiens.com/2013/02/13/How-I-Work-With-Postgres/
