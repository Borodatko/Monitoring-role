Monitoring
==========

Ansible role for Prometheus, Alert Manager, Grafana installation & configuration.


Dependencies
------------

 - RHEL7-based OS


Role Variables
--------------

| Name | Description | Type | Default Value|
|------|-------------|------|---------|
| ***defaults/main.yml*** |
| arch | architecture  | string | linux-amd64 |
| bin_path | path to binary  | string | /usr/local/bin |
| tmp_path | temporary path  | string | /tmp |
| ***prometheus.yml*** |
| prometheus_version | prometheus version | string | 2.37.0-rc.0 |
| prometheus_archive | prometheus downloaded archive | string | {{ tmp_path }}/prometheus-{{ prometheus_version }}.{{ arch }}.tar.gz |
| prometheus_path_tmp | prometheus temporary path | string | {{ tmp_path }}/prometheus-{{ prometheus_version }}.{{ arch }} |
| prometheus_path_conf | prometheus config file path | string | /etc/prometheus |
| prometheus_path_db | prometheus database path | string | /var/lib/prometheus |
| ***alertmanager.yml*** |
| alertmanager_version | alertmanager version | string | 0.24.0 |
| alertmanager_archive | alertmanager downloaded archive | string | {{ tmp_path }}/alertmanager-{{ alertmanager_version }}.{{ arch }}.tar.gz |
| alertmanager_path_tmp | alertmanager temporary path | string | {{ tmp_path }}/alertmanager-{{ alertmanager_version }}.{{ arch }} |
| alertmanager_path_conf | alertmanager config file path | string | /etc/alertmanager |
| ***exporter.yml*** |
| exporter_version | prometheus node exporter version | string | 1.3.1 |
| node_exporter_archive | downloaded archive | string | {{ tmp_path }}/node_exporter-{{ node_exporter_version }}.{{ arch }}.tar.gz |
| node_exporter_path_tmp | temporary path | string | {{ tmp_path }}/node_exporter-{{ node_exporter_version }}.{{ arch }} |
| systemd_path | systemd unit file path | string | /etc/systemd/system |
| ***grafana.yml*** |
| repo_path | path to repositories directory | string | /etc/yum.repos.d |
| basic_user | datasource basic auth username | string | CHANGEME |
| basic_pass | datasource basic auth password | string | CHANGEME |
| grafuser | grafana user | string | admin |
| grafpassword | grafana password | string | admin |
| mysql_db_addr | database address with port (example: "10.10.10.10:3306") | url | CHANGEME |
| mysql_database | database name | string | CHANGEME |
| mysql_user | database user | string | CHANGEME |
| mysql_pass | database password | string | CHANGEME |
| ***template variables*** |
| host_nginx | server ip address (nginx) | string | CHANGEME |
| host_db1 | server ip address (mysql_master) | string | CHANGEME |
| host_db2 | server ip address (mysql_slave) | string | CHANGEME |
| host_app | server ip address (wordpress) | string | CHANGEME |
| host_gitlab | server ip address (gitlab-ce) | string | CHANGEME |
| host_runner | server ip address (gitlab-runner) | string | CHANGEME |
| host_database | server ip address (mysql_master) | string | CHANGEME |
| email_recepient | recepient's address | string | CHANGEME |
| email_sender | sender's address | string | CHANGEME |
| email_smtp_server | smtp server address:port | string | smtp.mail.ru:465 |
| email_auth_username | smtp auth username | string | CHANGEME |
| email_auth_password | smtp auth password | string | CHANGEME |


Example Playbook
----------------

```yaml
- name: Monitoring Provisioning
  hosts: monitoring
  roles:
    - Monitoring-role
```

License
-------

BSD-3-Clause


Author Information
------------------

Borodatko
