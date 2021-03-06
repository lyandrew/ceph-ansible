# Ansible role: Ceph common

This role does several things prior to bootstrap your Ceph cluster:

* Checks the system and validate that Ceph can be installed
* Tunes the operating system if the node is an OSD server
* Installs Ceph
* Generates the `ceph.conf`

# Requirements

Nothing, it runs out of the box.

# Role variables

Have a look at: `defaults/main.yml`.

## Mandatory variables

* Installating source, chose one of these:
  * `ceph_stable`
  * `ceph_dev`
  * `ceph_stable_ice`
  * `ceph_stable_rh_storage`
* `journal_size`
* `monitor_interface`
* `cluster_network`

## Handlers

* restart ceph-mon
* restart ceph-osd
* restart ceph-mds
* restart ceph-rgw
* restart ceph-restapi

# Dependencies

None.

# Example Playbook

```
- hosts: servers
  remote_user: ubuntu
  roles:
     - { role: leseb.ceph-common }
```

# Misc

This role is a **mandatory** dependancy for the following roles:

* ceph-mon
* ceph-osd
* ceph-mds
* ceph-rgw
* ceph-restapi

# Contribution

**THIS REPOSITORY DOES NOT ACCEPT PULL REQUESTS**
**PULL REQUESTS MUST GO THROUGH [CEPH-ANSIBLE](https://github.com/ceph/ceph-ansible)**

# License

Apache

# Author Information

This role was created by [Sébastien Han](http://sebastien-han.fr/).
