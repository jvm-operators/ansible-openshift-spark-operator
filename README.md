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

or with your own settings (these are the default settings):

```yaml
- hosts: localhost
  roles:
    - role: jiri_kremser.spark_operator
      namespace: myproject
      image: quay.io/radanalyticsio/spark-operator:latest-released
      crd: false
      prometheus: false
      runExampleCluster: false
```

```bash
ansible-playbook example-playbook.yaml
```

or with this one liner:

```bash
ansible localhost -m include_role -a name=jiri_kremser.spark_operator
```

After running the playbook, the operator should be up and running and you can continue with creating either config maps
or custom resources for your Spark clusters or Spark applications. For more details please consult the 
[readme](https://github.com/radanalyticsio/spark-operator/blob/master/README.md) of spark-operator 
(you can skip the operator deployment step) or check the [examples](https://github.com/radanalyticsio/spark-operator/tree/master/examples).


### Try locally

```bash
ansible-playbook -i tests/inventory tests/test-playbook.yml
```
