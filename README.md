# Ansible Collection - mohit_jangir.Hadoop_HDFS_MapReduce_multi_node_cluster

Hadoop MapReduce and HDFS configuration
=========

This role will configure Hadoop Multi-Node MapReduce and HDFS cluster and connect them, and configure a client to perform further operations.


System requirements:
-------------------

- Deployment environment must have Ansible 2.9.0+
- Master and nodes must have passwordless SSH access


Have atleast 5 instances ready to be configured as namenode, datanode, jobtracker, tasktracker and a client. We can use as many datanodes and tasktrackers required.

The machine where this role will be executed needs to have
hadoop and jdk rpm in /root.


Dependencies
------------

We need to include all the 5 Roles From the Collection And System should have Ansible >=2.10.7


Verification
------------

```
1) hadoop dfsadmin -report

2) hadoop job -list-active-trackers

```



Example Playbook
----------------

create the setup.yml file like-

```
- hosts: all
  roles:
  - role: "<path-of-role-folder>"

```

create the ansible.cfg file like-

```
[defaults]
host_key_checking = False
roles = <path-of-role-folder>
inventory = <path-of-inventory-file>
ask_pass = False
remote_user = ec2-user
private_key_file = <path-of-key-file>
[privilege_escalation]
become = True
become_method = sudo
become_user = root
become_ask_pass = False
```

Run the Setup PlayBook with the following -

```
ansible-playbook <path-of-setup.yml>
```

License
-------

Apache-2.0

Author Information
------------------

MOHIT JANGIR

Email: mohitjangir700@gmail.com


Original-GitHub-SCM-Repo: https://github.com/MOHIT-JANGIR/HADOOP-HDFS-MapReduce-MULTI-NODE-CLUSTER.git


## Get Involved:
*  Read [Community Guidelines](<https://github.com/MOHIT-JANGIR/HADOOP-HDFS-MapReduce-MULTI-NODE-CLUSTER/blob/main/CONTRIBUTING.md>) for all
   kinds of ways to contribute to and interact with the project,
   including how to submit bug reports and
   code to repository.
*  Submit a proposed code update through a pull request to the ``master`` branch.
*  Talk to the owner before making larger changes
   to avoid duplicate efforts. This not only helps everyone
   know what is going on, it also helps save time and effort if we decide
   some changes are needed.
