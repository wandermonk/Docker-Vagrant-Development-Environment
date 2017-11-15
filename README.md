# Personal Vagrant Development Environment

Creates a Vagrant machine running on Windows, with the following auto-installed and configured. This is originally created by dcwangmit01(David Wang).
The setup.sh and other conigs are tweaked to work with windows.

* Docker Tools: docker, docker-compose
* Kubernetes Tools: kubectl, minikube, helm, kops
* Cloud tools: Terraform
* Amazon AWS Cloud Tools: awscli, ecs-cli
* Google Cloud Tools: gcloud
* Vmware Tools: govc
* Languages: golang, nodejs
* Programming tools: hub, direnv, virtualenv, jinja2, yq, gitslave, emacs
* Network Tools: nmap, traceroute, whois
* Golang Tools: glide, protocol buffers

For your dotfiles and dotdirectories in `~/`, it creates files or directories
in /vagrant/custom, and then symbolically links from `~/`.  This ensures that
your configuration files are persisted on the host, between rebuilding of
vagrant machines.

# Preparing your box for Vagrant

# Prerequisites

* Install virtualbox 5.1.26
* Install git bash for executing linux commands on windows
* Install nodejs 4.6.7
* Install nodejs 9.1.0
* Install golang

Before running the below commands open git bash as administrator user.

* Install Vagrant 2.0.1

* Install vbguest plugin -- Keeps virtualbox guest tools in sync with your version of virtualbox

     vagrant plugin install vagrant-vbguest

* Install cachier plugin (caches the APT, download, and Maven resources so that the box builds faster)

    vagrant plugin install vagrant-cachier
    
* To start the vagrant instance and accessing or provisioning via virtualbox

    vagrant up --provider virtualbox 
    
* To delete the existing vagrant image

    vagrant destroy -f 
    
* To convert remove hidden windows characters 

    dos2unix bin/minikube_init
    dos2unix bin/secure
    dos2unix conf/setup.sh
   
* Download go packages 

    go get -u github.com/github/hub
    go get -u github.com/vmware/govmomi/govc




