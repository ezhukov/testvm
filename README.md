## Rebuilding reverse build dependencies of a package

A virtual machine image is created with vmdebootstrap and started with kvm.
The specified package then checked out with debcheckout, built and all binaries
installed.
Reverse build dependencies of that package are found with build-rdeps tool,
then checked out with debcheckout and built.
All of the above is managed by ansible.

### Prerequisites

At least the following packages need to be installed:
 * qemu-kvm
 * ansible
 * vmdebootstrap

### How to use

First create a virtual machine by running (requires sudo privileges):

    $ ansible-playbook -K -i inventory vm.yml

Then specify a package name in the inventory file and run:

    $ ansible-playbook -i inventory provision.yml

If playbook execution fails - just ssh to the VM to fix the problem, the password
is 'changeit':

    $ ssh -p 2222 testvm@127.0.0.3
Then re-run the playbook. The playbooks are idempotent and build avoidance is in
place.
