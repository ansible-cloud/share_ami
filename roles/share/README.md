# ansible_cloud.share_ami role

This role will share AMIs with other AWS accounts.  Please see root README.md for additional info!

# Requirements

You need two things:

1. a list of AMIs you want to share

```
my_ami_list:
  ap-northeast-1: ami-0c76633109ab40fc
  eu-central-1: ami-00690163363bc33b2
  us-east-1: ami-0863330c9057acd1
```

2. a list of Account IDs you want to share the AMIs to

```
account_list:
  - "11463example"
  - "90073example"
  - "71963example"
  - "07923example"

```

## Example task calling this role:

```
- name: backup configuration
  include_role:
    name: ansible_cloud.share_ami.share"
  vars:
    user_id_list: "{{ account_list }}"
    ami_list: "{{ my_ami_list }}"
```

## Full playbook example

```
- name: share custom amazon machine images (AMIs) to other AWS accounts
  hosts: localhost
  connection: local
  become: false
  gather_facts: false
  tasks:
    - name: share ami
      include_role:
        name: ansible_cloud.share_ami.share
      vars:
        user_id_list: "{{ account_list }}"
        ami_list: "{{ my_ami_list }}"
```
