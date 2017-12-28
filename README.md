# "Infrastructure as Code" for Redmine

## Platform

- Amazon Web Service EC2

## Dependencies

- git
- ansible

### install git

```bash
$ sudo yum install git
```

### install ansible

```bash
$ sudo pip install ansible
```

## Configure

Modify inventory/hosts file.

```ini
; target hosts
[redmine]
localhost

; variables
[redmine:vars]
; required
ansible_connection=local

; system user
user=redmine
; system user password
pass=password
; system user group
group=redmine
; install mysql version
mysql_version=55
; database root user password
db_root_pass=password
; database schema
db_schema=redmine
; database user
db_user=redmine
; database password
db_pass=password
; database charset
db_charset=utf8mb4
; email address (account)
email=sample@gmail.com
; email server
email_server=smtp.gmail.com
; email server port
email_port=587
; email account password
email_pass=password
; install ruby version
ruby_version=2.4.3
```

## Installation

```bash
$ git clone https://github.com/april418/redmine-playbook.git
$ cd redmine-playbook
$ ansible-playbook main.yml -i inventory/hosts
```

