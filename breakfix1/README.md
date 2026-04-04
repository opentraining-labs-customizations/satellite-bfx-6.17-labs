breakfix0/SCENARIO_DNF
=========

This role registers a RHEL8 client to satellite and simulates few problems with installing katello-pull-transport-migrate via DNF.

What we essentially do by this ansible role is:

* Confirm that the satellite is running
* Sync the satellite-client repo in immediate mode
* Does a rm -rf on /var/lib/pulp/media/artifacts/*
* Creates a LCE and adds it to capsule.
* Creates a cv for that LCE with the required repos and it gets automatically synced to capsule
* Creates registration command for a RHEL8 node to the capsule and registers it.


Requirements
------------

This ansible role requires the [foreman ansible modules](https://github.com/theforeman/foreman-ansible-modules/). Please install them before executing the role.

Role Variables
--------------

The `vars/main.yml` file contains the required variables for the ansible role. Adjust the values according to your environment.

Dependencies
------------

NA

Example Playbook
----------------

This ansible role can be executed after creating a playbook in the following way. 

~~~
# cat breakfix1.yaml
---
- name: Deploy ansible role breakfix0 on target systems
  hosts: satellite
  roles:
    - role: breakfix1
      tags: break
~~~

License
-------

It is free software licensed under the terms of the GNU General Public License GPL v3 or later. A copy of the license can be obtained here: http://www.gnu.org/licenses/gpl-3.0.html

Author Information
------------------

This role is developed by Soham Majumdar <smajumda@redhat.com>, <csedeepm@gmail.com>. 
