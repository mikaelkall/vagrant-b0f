# -*- mode: ruby -*-
# vi: set ft=ruby :

# Turn of ASLR
$script = <<SCRIPT
  echo Turns off ASLR...
  echo 0 > /proc/sys/kernel/randomize_va_space
  apt-get -y install gdb radare2 nasm
SCRIPT

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty32"
  config.vm.provision "shell", inline: $script
end
