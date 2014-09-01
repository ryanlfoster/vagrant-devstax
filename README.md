#vagrant-devstax

Vagrant + Chef Developer Stacks

## Setup On Windows

* Download and install [ChefDK](http://downloads.getchef.com/chef-dk/windows/)
This should install an embedded version or Ruby. Make sure that it is resolved correctly by using the following command
```shell
C:\> where ruby
C:\opscode\chefdk\embedded\bin\ruby.exe
```
You can verify the installation with this command
```shell
C:\> chef verify
```
* Download and install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

* Download and install [Git](http://msysgit.github.io/)
Make sure the git command is available from your command pompt by choosing to include it in your PATH during installation.

* Download and install [Vagrant](https://www.vagrantup.com/downloads.html)
You will need to install the following Vagrant plugins
```shell
C:\> vagrant plugin install vagrant-hostmanager
C:\> vagrant plugin install vagrant-berkshelf
C:\> vagrant plugin install vagrant-hostmanager
C:\> vagrant plugin install vagrant-omnibus
C:\> vagrant plugin install vagrant-vbguest
```