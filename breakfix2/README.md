breakfix2/SCENARIO_PGSQL
========================

The role breaks the Satellite by modifying the HBA configuration and the filesystem permissions of the PostgreSQL data directory.

The role performs the following:

* Creates a new HBA configuration that rejects the connection to PostgreSQL instance on the Satellite.
* Changes the filesystem permissions of the PostgreSQL data directory.
* Reboots the system.

Requirements
------------

This Ansible role requires the following collections:

 * theforeman.foreman
 * community.general

Ensure these are installed before executing the role.

Role Variables
--------------

NA

Dependencies
------------

NA

Example Playbook
----------------

To use this role, create a playbook as shown in the following example:

~~~
# cat breakfix2.yaml
---
- name: Deploy ansible role breakfix2 on target systems
  hosts: satellite
  become: True
  roles:
    - role: breakfix2
      tags: break
~~~

License
-------

It is free software licensed under the terms of the GNU General Public License GPL v3 or later. A copy of the license can be obtained here: http://www.gnu.org/licenses/gpl-3.0.html

Author Information
------------------

This role is developed by Manu Sunil <msunil@redhat.com> and Soham Majumdar <smajumda@redhat.com>.
