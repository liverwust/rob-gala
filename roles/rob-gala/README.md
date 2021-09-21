Role Name
=========

Configure Rob's Ubuntu instance to run a Gala Founder's Node.

Requirements
------------

There needs to be a basic Ubuntu VM running in order to host this
service. One way to accomplish this, particularly on Rob's server
(VAL-JEAN), is to install the Ubuntu image from the [Hyper-V
Gallery][1].

The VM needs to be attached to a bridged "external" network so that it
can acquire an IP address from the router via DHCP, and be accessible
by a separate IP from the host computer.

[1]: https://docs.microsoft.com/en-us/virtualization/community/team-blog/2017/20170726-hyper-v-virtual-machine-gallery-and-networking-improvements

Role Variables
--------------

The following host_vars need to be specified (ideally in a file
protected by Ansible Vault):

* gala_linux_user: user account on the Gala Linux host
* gala_linux_pass: password for the Gala Linux host
* gala_email: e-mail address for the Gala account
* gala_password: password for that same account
* gala_node_specifier: For running multiple nodes in parallel; see
  [ewrogers' documentation][2] for info, or just set to 1 if running
  a single node
* gala_machine_id: Generate this once with `dbus-uuidgen` and store it
  with the Ansible vault file

[2]: https://github.com/ewrogers/gala-docker

Dependencies
------------

Install the following Ansible Galaxy role(s) with
```
ansible-galaxy install -r meta/requirements.yml
```

* gantsign.minikube

Example Playbook
----------------

See site.yml in the top-level directory.

License
-------

BSD

Author Information
------------------

Louis Wust <louiswust@fastmail.fm>
