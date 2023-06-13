# Vagrant Home Lab Demo

## Description

This repository contains the code for the "Your Ultimate Virtual Home Lab - Vagrant Setup Made Easy" video. 

With Vagrant, you can easily create and manage virtual machines for testing and development purposes. The code in this repository will guide you through the process step-by-step, from installing Vagrant to creating your first virtual machine. By following the instructions in this repository, you will have your own virtual home lab up and running in no time, ready for you to experiment with and learn new skills.

## Steps

### Download and install Vagrant

Download and install Vagrant from the [official website](https://developer.hashicorp.com/vagrant/downloads).

***Your computer may require a restart after installing Vagrant.***

You can run the command `vagrant --version` to verify that Vagrant has been installed correctly.

### Install a virtualization provider

I am using VirtualBox as my virtualization provider, but you can use any provider supported by Vagrant. You can find a list of supported providers [here](https://www.vagrantup.com/docs/providers/).

### Initialize a Vagrant project

Run the command `vagrant init` to initialize a Vagrant project.

This will create a file called `Vagrantfile` in the current directory.

### Add the Vagrant boxes using the Vagrant CLI

For each box that you want to add from the [hashicorp catalog](https://app.vagrantup.com/boxes/search), run the command `vagrant box add <box-name>`.

In this tutorial we will be adding the following boxes:

- Ubuntu 18.04
- CentOS 7.0

The following commands will add the boxes to your Vagrant environment:

```console
vagrant box add generic/ubuntu1804
vagrant box add centos/7
```

***Notice that you make sure to specify the correct provider when adding the boxes.***

To ensure that the boxes have been added correctly, you can run the command `vagrant box list`.

### Configure the Vagrantfile

Refer to the `Vagrantfile` in this repository for an example of how to configure your Vagrantfile.

Notice that the `Vagrantfile` uses dynamic configuration to allow for the creation of multiple virtual machines.

### Create the virtual machines

Run the command `vagrant up` to create the virtual machines.

If any changes are made to the `Vagrantfile`, you can run the command `vagrant reload` to apply the changes.

***Notice that `vagrant reload` is the equivalent of running `vagrant halt` followed by `vagrant up`.***

### Connect to the virtual machines

Run the command `vagrant ssh <vm-name>` to connect to the virtual machines.

### Destroy the virtual machines

Run the command `vagrant destroy` to destroy the virtual machines.

## What's next?

Now that you have your own virtual home lab up and running, you can start experimenting with different configurations and technologies.

One natural next step would be to install a provisioning tool such as Ansible on your host machine and use it to configure the virtual machines further. Stay tuned for a future video where I will show you how to do this.

## Additional Resources

- [Vagrant Documentation](https://www.vagrantup.com/docs)
- [Vagrant Getting Started Guide](https://www.vagrantup.com/docs/getting-started)
- [Vagrant Boxes](https://app.vagrantup.com/boxes/search)
- [Vagrant CLI](https://www.vagrantup.com/docs/cli)
- [Vagrant Networking](https://www.vagrantup.com/docs/networking)
