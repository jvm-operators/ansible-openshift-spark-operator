## Info
[![Build status](https://travis-ci.org/jvm-operators/ansible-openshift-spark-operator.svg?branch=master)](https://travis-ci.org/jvm-operators/ansible-openshift-spark-operator)
[![Ansible Downloads](https://img.shields.io/ansible/role/d/32399.svg)](https://galaxy.ansible.com/jiri_kremser/spark_operator)


Ansible role for deploying [spark-operator](https://github.com/radanalyticsio/spark-operator). 

It is available also on Ansible Galaxy ([link](https://galaxy.ansible.com/jiri_kremser/spark_operator)).

## Usage
```bash
ansible-galaxy install jiri_kremser.spark_operator
```

And then use it in your playbook (`example-playbook.yaml`):

```yaml
- hosts: localhost
  roles:
    - role: jiri_kremser.spark_operator
```

or with your own settings:

```yaml
- hosts: localhost
  roles:
    - role: jiri_kremser.spark_operator
      namespace: myproject
      image: quay.io/radanalyticsio/spark-operator:latest-released
      crd: "false"
```

```bash
ansible-playbook example-playbook.yaml
```