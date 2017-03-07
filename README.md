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

### Known limitations

 * currently only architecture type 'all' is supported
 * 'build-rdeps --only-main --old' is used to find package reverse build dependencies

### Advantages of this solution

If playbook execution fails - just ssh to the VM to fix the problem, the password
is 'changeit':

    $ ssh -p 2222 testvm@127.0.0.3
Then re-run the playbook. The playbooks are idempotent and build avoidance is in
place.
