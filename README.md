Role Name
=========

ansible role for creating a multi-node capi mgmt cluster. This role create instances on an existing openstack instances which will be the capi mgmt cluster used with magnum

Requirements
------------

This ansible role requires:
- openstacksdk to be installed 
- openstack.cloud ansible collection to the installed
- the node from where the playbooks run should have acess to the openstack public endpoints
- admin access to the environment; the resources (instances, ports, volumes etc) will be created in the admin tenant

Role Variables
--------------

The ansible role has many variables which can be defined including cidr for the subnet, volume size, volume types etc; There are a few important ones mentioned here:
- "ext_net_id": this is the variable which expects a pre-created neutron network from where the floating ip(s) will be created; also this network should be reachable from the
node from where the public is run
- "capi_mgmt_dns_servers": this is the dns server which will be used for the capi mgmt cluster vms; this should be reachable from the vms themselves
- "capi_mgmt_cluster_volume_type": set this to the volume type according to the environment (default is set to "lvmdriver-1")

Dependencies
------------

There are no external role dependencies

Example Playbook
----------------

An example playbook has been included in the role itself (playbook.yaml); provide the admin user password while running the playbook with
-e os_password="passwd"

License
-------

MIT

Author Information
------------------

Punit Shankar Kundal
punitshankar.kundal@rackspace.com
