# ansible_cloud.share_ami

This is an Ansible content collection for sharing custom amazon machine images (AMIs).  

## Table of Contents
* [Using in Automation controller](#using-in-automation-controller)
* [Requirements](#requirements)
* [How to use:](#how-to-use)
  * [Example task calling this role:](#example-task-calling-this-role)
  * [Full playbook example](#full-playbook-example)
* [See Also:](#see-also)
* [More information about contributing](#more-information-about-contributing)
* [Licensing](#licensing)

# Using in Automation controller

You can also directly just use this collection as a project inside Automation controller (part of Red Hat Ansible Automation Platform).  Load the Github repository [https://github.com/ansible-cloud/share_ami](https://github.com/ansible-cloud/share_ami) as a project inside automation controller and select the `share_ami.yml` playbook and set the two variables listed below.  You do NOT need to install the collection to use it directly but you WILL need the `amazon.aws` collection installed.

# Requirements

You need three things:

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

3. The collection [amazon.aws](https://github.com/ansible-collections/amazon.aws/blob/main/README.md) installed. (`ansible-galaxy collection install amazon.aws`)

# How to use:

If you are using this collection you need to install it.

```
ansible-galaxy collection install ansible_cloud.share_ami
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

# See Also:

* [Amazon Web Services Guide](https://docs.ansible.com/ansible/latest/scenario_guides/guide_aws.html)
* [Ansible Using collections](https://docs.ansible.com/ansible/latest/user_guide/collections_using.html) for more details.

You can also join us on [Slack](https://join.slack.com/t/ansiblenetwork/shared_invite/zt-3zeqmhhx-zuID9uJqbbpZ2KdVeTwvzw)

# More information about contributing

- [Ansible Community Guide](https://docs.ansible.com/ansible/latest/community/index.html) - Details on contributing to Ansible
- [Contributing to Collections](https://docs.ansible.com/ansible/devel/dev_guide/developing_collections.html#contributing-to-collections) - How to check out collection git repositories correctly

# Licensing

GNU General Public License v3.0 or later.

See [COPYING](https://www.gnu.org/licenses/gpl-3.0.txt) to see the full text.
