# ansible_cloud.share_ami

collection for sharing custom amazon machine images (AMIs)


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
  - "114320544164"
```

# How to use:

```
- name: backup configuration
  include_role:
    name: ansible_cloud.share_ami.share"
  vars:
    user_id_list: "{{ account_list }}"
    ami_list: "{{ my_ami_list }}"
```
