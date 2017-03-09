# testvm
Rebuilding reverse build dependencies of a package

### Prerequisites

At least the following packages need to be installed:
 * qemu-kvm
 * ansible
 * vmdebootstrap

### How to use

    $ ansible-playbook -K -i invent book.yml
    $ ansible-playbook -i invent testvm.yml --extra-vars package=your-package-name

If playbook execution fails - just ssh to the VM to fix the problem, the password
is 'changeit':

    $ ssh -p 2222 testvm@127.0.0.3
Then re-run the playbook. The playbooks are idempotent and build avoidance is in
place.

### About this solution

The reverse build dependencies of a package are found with build-rdeps tool.
