breakfix0/SCENARIO_CANDLEPIN
=========

This role simulates problems with candlepin on satellite arising from hardening [permission issues] or data corruption.

What we essentially do by this ansible role is:

* Confirm that the satellite is running
* Modify file permissions and ownerships or config & log files of candlepin
* Corrupt active mq files


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
# cat breakfix0.yaml
---
- name: Deploy ansible role breakfix0 on target systems
  hosts: satellite
  roles:
    - role: breakfix0
      tags: break
~~~

License
-------

It is free software licensed under the terms of the GNU General Public License GPL v3 or later. A copy of the license can be obtained here: http://www.gnu.org/licenses/gpl-3.0.html

Author Information
------------------

This role is developed by Sayan Das <saydas@redhat.com>
