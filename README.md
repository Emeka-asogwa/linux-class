# linux-class
## Environment Setup 

We will be using different applications throughout this DevOps class. Getting the right installation package for your computer is the first step to learning how to use the application. During installation, choose the appropriate OS package and install/download. 

Please download and install below packages:
1. Git bash 
https://git-scm.com/download/win
2. kubernetes
https://kubernetes.io/releases/download/


3. minikube
https://minikube.sigs.k8s.io/docs/start/

To start minikube, type 
`minikube start`

4. Docker Desktop (This is used for running a container)
https://docs.docker.com/engine/install/

Create an account on docker Hub. Login to the Docker Desktop using the new created account info. 

5. GitHub - Please create account on gitbub. Github is used for storing of codes, enabling versioning of codes and collaborating on a project. 
https://github.com/ 

6. Virtual Studio (For scripting)
https://code.visualstudio.com/download

7. Virtual Box - (We will use this to house our virtual machines)
https://www.virtualbox.org/wiki/Downloads

8. Microsoft Visual C++ Redistributable - (If you don't have it yet)
https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170


9. Vagrant (choose Windows, Linux or MacOs as appropriate to your computer)
https://developer.hashicorp.com/vagrant/install

After installing vagrant, open `git bash` and type:
`cd ~/`
`touch Vagrantfile`
Open the `Vagrantfile` file create and paste below:


# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "vm1" do |vm1|
    vm1.vm.box = "ubuntu/bionic64"
    vm1.vm.network "private_network", ip: "192.168.50.101"
    vm1.vm.provider "virtualbox" do |vb|
      vb.name = "VM1"
      vb.memory = "1024"
    end
  end

  config.vm.define "vm3" do |vm3|
    vm3.vm.box = "Fedora 35"
    vm3.vm.network "private_network", ip: "192.168.50.102"
    vm3.vm.provider "virtualbox" do |vb|
      vb.name = "VM3"
      vb.memory = "1024"
    end
  end

  config.vm.define "vm2" do |vm2|
    vm2.vm.box = "generic/rhel8"
    vm2.vm.network "private_network", ip: "192.168.50.103"
    vm2.vm.provider "virtualbox" do |vb|
      vb.name = "VM2"
      vb.memory = "1024"
    end
  end
end


We will be working on during machines. The first machine (vm1) is an `ubuntu` machine, the second (vm2) is a `Red hat` machine while the third (vm3) is `Fedora 35`. 

To start the vms (vm1, vm2, and vm3), run :

`vagrant up`

Note: If the three machines do not start up, considering runing them individually as vagrant up vm1, vagrant up vm2 or vagrant up vm3. 

To login to the Vm, type :
`vagrant ssh <vm name> `

For example, to login to vm1, type :
vagrant ssh vm1

To login to vm2, first logout from vm1 by typing 
`logout` then 
`vagrant ssh vm2`








