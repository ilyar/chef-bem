# Chef kitchen for BEM

## [BEM](http://ru.bem.info) development on a virtual machine with Vagrant

### Requirements

* [VirtualBox](https://www.virtualbox.org)
* [Vagrant 1.3.x](http://vagrantup.com)

Make sure to use Vagrant v1.3.x. Do not install Vagrant via rubygems.org as there exists an old gem which will probably cause errors. Instead, go to [Vagrant download page](http://downloads.vagrantup.com/) and install a version ~> `1.3.0`.

### Testing Vagrantfile

    git clone https://github.com/ilyar/chef-bem.git
    cd chef-bem/tests
    vagrant up
    # If need customize virtual machine
    BEM_VM_MEMORY=512 BEM_VM_CORES=2 vagrant up

Open console virtual machine

    vagrant ssh
    bem server
    # open http://localhost:3000/desktop.bundles/index/
    # bem coding

### Aliases

*bemblock* `bem create -l desktop.blocks/ -b`
*bempage* `bem create -l desktop.bundles/ -b`

## Backlog

Feature request and bug report https://github.com/ilyar/chef-bem/issues