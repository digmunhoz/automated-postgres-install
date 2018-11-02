# Automated Postgres Server Install

This project has as an objective to create a Postgres server completely automated using [`Ansible`](https://www.ansible.com/) with a playbook.

Install a Postgres server from zero was never easier like now.

Here we're managing things like:

* Kernel tunings
* Transparent Hugepage
* Utilities like `pg_activity` and `pgbouncer`
* Postgres necessary packages

> At this moment, this project works only installing the Postgres 9.5 on Amazon Linux. Soon, we're gonna allow more Linux systems and define the postgres version as variable to be more flexible.

## Prerequisites

All you need is to have [`ansible`](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) installed on your computer.

> You'll also need to have SSH access to the target server (new Postgres server)

## Running the process

As soon you have with the server ready to receive the install process, it's just to call the playbook informing the IP Address and the SSH user whose can execute command with `sudo`.

The command to call the playbook is the following (lets supose that the server IP is `172.31.0.10` and the SSH user is `ec2-user`):

### Without SSH Key

```
ansible-playbook playbook.yml --inventory "172.31.0.10," --user ec2-user
```

### With SSH Key

```
ansible-playbook playbook.yml --inventory "172.31.0.10," --private-key SOME_SSH_KEY.pem --user ec2-user
```

> Don't forget the comma after the IP Address on the `--inventory` argument.

## Authors

* **Diogo Munhoz Fraga** - [digmunhoz](https://github.com/digmunhoz)
