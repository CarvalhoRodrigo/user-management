Role Name
=========

Creating and configuring user.

Requirements
------------

No requirements.

Role Variables
--------------

You must set a list of groups and users with options.

sample:

```yaml
list_of_groups:
   - group1
   - group2

list_of_users:
  - name: user1
    group: group1
    sudo: yes
    public_key_path: ../secrets/user1.key.pub
  - name: user2
    group: group2
    sudo: no
    public_key_path: ../secrets/user2.key.pub
```

Dependencies
------------

No dependencies.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: servers
  become : yes
  tasks:
    - name: Add and configure user
      include_role:
        name: sab-user-management-role
      vars:
        list_of_groups:
          - group1
          - group2
        list_of_users:
          - name: user1
            group: group1
            sudo: yes
            public_key_path: ../secrets/user1.key.pub
          - name: user2
            group: group2
            sudo: no
            public_key_path: ../secrets/user2.key.pub
```

License
-------

GPLv3

Author Information
------------------

Mikael LE BERRE
