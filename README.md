# ansible_cloud.share_ami

This is an Ansible content collection for sharing custom amazon machine images (AMIs). If you are using this collection you need to install it.

```
ansible-galaxy collection install ansible_cloud.share_ami
```

## Table of Contents
* [Using in Automation controller](#using-in-automation-controller)
* [copy AMI](#copy-ami)
* [share AMI](#share-ami)
* [Requirements](#requirements)
* [How to use:](#how-to-use)
* [See Also:](#see-also)
* [More information about contributing](#more-information-about-contributing)
* [Licensing](#licensing)
<!-- /TOC -->

# Using in Automation controller

You can also directly just use this collection as a project inside Automation controller (part of Red Hat Ansible Automation Platform).  Load the Github repository [https://github.com/ansible-cloud/share_ami](https://github.com/ansible-cloud/share_ami) as a project inside automation controller and select the `share_ami.yml` playbook or the `copy_ami.yml` playbook. Make sure to set the variables listed in the role documentation.  You do NOT need to install the collection to use it directly but you WILL need the `amazon.aws` collection installed.

# copy AMI

This role will copy specified AMIs to other regions and return a list of the new AMI info.  It can take a list of AMIs and their existing region and copy to a list of regions.

[Documentation for ansible_cloud.share_ami.copy](roles/copy/README.md)

# share AMI

This role will share private AMIs with specified accounts.

[Documentation for ansible_cloud.share_ami.share](roles/share/README.md)

# Requirements

The collection [amazon.aws](https://github.com/ansible-collections/amazon.aws/blob/main/README.md) installed. (`ansible-galaxy collection install amazon.aws`)

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
