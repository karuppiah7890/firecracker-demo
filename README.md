# firecracker-demo

This is a demo to show how to run firecracker in a
[VirtualBox](https://www.virtualbox.org/) VM

I'm using macOS Catalina `Version 10.15.4 (19E266)` and VirtualBox
`Version 6.1.4 r136177 (Qt5.6.3)`. I'm going to be using
[`vagrant`](https://www.vagrantup.com/) to manage my VirtualBox VMs, and it's
version is `2.2.7`

Now, let's get started! These are the steps to follow:

```
$ # first clone this repo!
$ git clone https://github.com/karuppiah7890/firecracker-demo
$ # get inside the repo
$ cd firecracker-demo
$ # now let's start our VM
$ # choose VirtualBox if it asks what provider
$ vagrant up
$ # if the vagrant box is not present,
$ # it will first download that and then
$ # start the VM.
$ # Once it's done starting, check status
$ vagrant status
$ # if you can see it's running, all good
$ # Now let's SSH into the VM! :D
$ vagrant ssh
$ # Now you are inside the VM. Every command
$ # below is meant to be typed inside the VM.
$ # Now we are going to check if our CPU supports
$ # KVM extensions. For this we need to use a
$ # command called "kvm-ok". Let's install it
$ sudo apt update
$ sudo apt install cpu-checker
$ # yay, that's it. kvm-ok is installed
$ sudo /usr/sbin/kvm-ok
INFO: Your CPU does not support KVM extensions
KVM acceleration can NOT be used

$ # if you see the above message, you need
$ # to do more to support KVM extensions.
$ # But if you see that everything is okay,
$ # all cool! :)
```
