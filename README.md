# testvm
Rebuilding package build dependencies

## Running instructions

### 1. Create a VM

ansible-playbook -K -i invent book.yml

### 2. Build and install a package

ansible-playbook -i invent testvm.yml --extra-vars package=jing-trang
