# testvm
Rebuilding package build dependencies

## Running instructions

### 1. Create a VM

ansible-playbook -K -i invent book.yml

### 2. Build and install a package

ansible-playbook -i invent testvm.yml --extra-vars package=jing-trang

### 3. Known limitations

 * currently only architecture type 'all' is supported
 * if debcheckout fails, need to ssh to VM and get source
