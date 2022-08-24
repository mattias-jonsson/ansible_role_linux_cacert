Ansible Role: ansible_role_linux_cacert
=========

Handles custom CA certificates (install/blacklist) on the following Linux distributions:

<ul>
<li>Red Hat/CentOS/Fedora/etc.
<li>Debian/Ubuntu/etc.
</ul>

Requirements
------------

This role has no dependencies besides what is included in Ansible Core.

Role Variables
--------------

Available variables are listed below, along with default values where applicable (see defaults/main.yml):


    ansible_role_linux_cacert_list

Optional, list of CA certificate files to install.  

    ansible_role_linux_cacert_blacklist  

Optional, list of blacklist CA certificate files to install (currently only works on Enterprise Linux-based distributions).  

    ansible_role_linux_cacert_cleanup  

Optionally remove any certificate files not added by role from the `ansible_role_linux_cacert_dest_path` see the variable file in `vars` folder of the role.  


Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers

      vars:
        ansible_role_linux_cacert_list:
        - files/someCAcert.pem
        ansible_role_linux_cacert_blacklist:
        - files/someBlacklistedCAcert.pem
        ansible_role_linux_cacert_cleanup: true

      roles:
         - role: ansible_role_sudoers

License
-------

MIT

Author Information
------------------

Mattias Jonsson