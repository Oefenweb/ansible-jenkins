## jenkins

[![CI](https://github.com/Oefenweb/ansible-jenkins/workflows/CI/badge.svg)](https://github.com/Oefenweb/ansible-jenkins/actions?query=workflow%3ACI)
[![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-jenkins-blue.svg)](https://galaxy.ansible.com/Oefenweb/jenkins)

Set up (the latest version of) jenkins in Ubuntu systems.

#### Requirements

* `software-properties-common` (will be installed)
* `dirmngr` (will be installed)
* `apt-transport-https` (will be installed)
* `curl` (will be installed)
* `default-j(re|dk)` (will be installed when `jenkins_assume_java_provided` is `false` (default))

#### Variables

* `jenkins_install` [default: `[]`]: (Additional) Packages to install

* `jenkins_assume_java_provided` [default: `false`]: Whether or not to assume that java (`jre` and `jdk`) is already installed

* `jenkins_java_args` [default: `['-Djava.awt.headless=true']`]: Java arguments to pass
* `jenkins_user` [default: `jenkins`]: User to be invoked as
* `jenkins_group` [default: `jenkins`]: Group to be invoked as
* `jenkins_home` [default: `/var/lib/jenkins`]: Home directory (of jenkins user)
* `jenkins_http_port` [default: `8080`]: Port for HTTP connector
* `jenkins_ajp_port` [default: `-1`]: Port for AJP connector
* `jenkins_prefix` [default: `/jenkins`]: Servlet context, important if you want to use apache proxying
* `jenkins_args` [default: `["--webroot=/var/cache/{{ jenkins_name }}/war", '--httpPort=$HTTP_PORT']`]: Jenkins arguments to pass

* `jenkins_cli_path` [default: `/opt/jenkins`]: Client installation path

* `jenkins_plugins` [default: `[]`]: Plugins to install (**Does not work (for now)**)

* `jenkins_tasks_mailer_manage` [default: `true`]: Whether or not to manage `hudson.tasks.Mailer.xml` (for sending notifications)
* `jenkins_tasks_mailer_default_suffix` [default: `'@localhost.localdomain'`]: Default user e-mail suffix
* `jenkins_tasks_mailer_smtp_host` [default: `localhost`]: SMTP server
* `jenkins_tasks_mailer_smtp_port` [default: `25`]: SMTP port
* `jenkins_tasks_mailer_use_ssl` [default: `false`]: Whether or not to use ssl
* `jenkins_tasks_mailer_use_smtp_auth` [default: `false`]: Whether or not to use SMTP Authentication
* `jenkins_tasks_mailer_smtp_auth_username` [default: `''`]: SMTP Authentication username
* `jenkins_tasks_mailer_smtp_auth_password` [default: `''`]: SMTP Authentication password
* `jenkins_tasks_mailer_charset` [default: `UTF-8`]: Charset

## Dependencies

None

## Recommended

* `ansible-oracle-java` ([see](https://github.com/Oefenweb/ansible-oracle-java), when `jenkins_assume_java_provided` is `true`)

#### Example

```yaml
---
- hosts: all
  roles:
    - jenkins
```

#### License

MIT

#### Author Information

Mischa ter Smitten (based on work of [ICTO](https://github.com/ICTO/ansible-jenkins) and [geerlingguy](https://github.com/geerlingguy/ansible-role-jenkins))

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-jenkins/issues)!
