#vagrant-devstax

Vagrant + Chef Developer Stacks

## Setup On Windows

### ChefDK
Download and install [ChefDK](http://downloads.getchef.com/chef-dk/windows/) This should install an embedded version or Ruby.
Make sure that it is resolved correctly by using the following command
```shell
C:\> where ruby
C:\opscode\chefdk\embedded\bin\ruby.exe
```
You can verify the installation with this command
```shell
C:\> chef verify
```

### VirtualBox
Download and install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

### Git
Download and install [Git](http://msysgit.github.io/). Make sure the git command is available from your command pompt by choosing to include it in your PATH during installation.

### Vagrant
Download and install [Vagrant](https://www.vagrantup.com/downloads.html). You will need to install the following Vagrant plugins
```shell
C:\> vagrant plugin install vagrant-hostmanager
C:\> vagrant plugin install vagrant-berkshelf
C:\> vagrant plugin install vagrant-hostmanager
C:\> vagrant plugin install vagrant-omnibus
C:\> vagrant plugin install vagrant-vbguest
```

### Starting a VM
Assuming you checked out this repository to C:\vagrant-devstax
```shell
C:\> cd C:\vagrant-devstax
C:\vagrant-devstax> vagrant up <vagrant_name>
```
You can reference the Vagrantfile for the available vagrants