# ansible_cloud.share_ami.copy role

This role will copy AMIs within your AWS account from one region to another region.  Please see root README.md for additional info!

# Requirements

You need two things:

1. a list of AMIs you want to share

```
my_ami_list:
  ap-northeast-1: ami-0c76633109ab40fc
  eu-central-1: ami-00690163363bc33b2
  us-east-1: ami-0863330c9057acd1
```

2. a list of regions you want to copy to

```
my_copy_to_regions:
  - us-west-1
  - us-east-2
```

## Example task calling this role:

```
- name: copy amis to other regions
  include_role:
    name: ansible_cloud.share_ami.copy"
  vars:
    ami_list: "{{ my_ami_list }}"
    copy_to_regions: "{{ my_copy_to_regions }}"
```

## Full playbook example

```
- name: copy custom amazon machine images (AMIs) to other regions
  hosts: localhost
  connection: local
  become: false
  gather_facts: false
  tasks:
    - name: copy amis to other regions
      include_role:
        name: ansible_cloud.share_ami.copy"
      vars:
        ami_list: "{{ my_ami_list }}"
        copy_to_regions: "{{ my_copy_to_regions }}"
```
