# -*- mode: ruby -*-
# vi: set ft=ruby :

# Turn of ASLR
$script = <<SCRIPT
  echo Turns off ASLR...
  echo 0 > /proc/sys/kernel/randomize_va_space
  apt-get -y install gdb radare2 nasm g++
  cp -R /vagrant/vuln /tmp/
  echo Compiling source code
  for f in $(find /tmp/vuln -name Makefile -print); do cd $(dirname $f); pwd; make; done
  chown root /tmp/vuln/b0f/demo/vuln && chmod 4777 /tmp/vuln/b0f/demo/vuln
  ln -s /tmp/vuln /home/vagrant/vuln
SCRIPT

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty32"
  config.vm.provision "shell", inline: $script
end
