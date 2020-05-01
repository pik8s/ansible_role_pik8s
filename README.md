pik8s
=========
pik8s is designed to provision a single control plane Kubernetes cluster on Raspberry Pis' running Raspbian Lite.  The amount of options to configure the cluster have been kept to a minimum to reduce the barrier to entry.

pik8s is heavily influenced by [1] and [2].  This project differentiates itself by narrowing the scope of [1] and converting the work in [2] to an Ansible role.

```[1] https://github.com/geerlingguy/ansible-role-kubernetes
[2] https://github.com/rak8s/```


Requirements
------------
2 or more Raspberry Pi 3 or greater.


Role Variables
--------------

pik8s_docker_ce_version: This is the Major.Minor version of Docker CE to install.
pik8s_kubernetes_version: This is the Major.Minor version of kubeadm, kubectl, and kublet to install.

Dependencies
------------
No other roles are required.

Example Playbook
----------------
Playbook:

```yaml
---
- hosts: all
  become: true
  remote_user: pi

  roles:
    - role: nicholasburr.pik8s

```

Set the role for each machine in your inventory file. See the examples directory for more information.

Master inventory variable:
```yaml
pik8s_cluster_role: "master"
```

Worker inventory variable:
```yaml
pik8s_cluster_role: "worker"
```

License
-------

MIT

Author Information
------------------
