# vagrant-kernel-update

Operating System: Ubuntu 26.04 LTS  
Kernel: Linux 7.0.0-22-generic  

```bash
sudo apt update

sudo apt install -y vim

sudo apt install -y traceroute net-tools tcpdump

sudo apt install -y curl wget

sudo apt install -y git

sudo apt install -y dkms build-essential linux-headers-$(uname -r) gnupg

wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo gpg --dearmor -o /usr/share/keyrings/oracle-virtualbox.gpg

echo "deb [arch=amd64 signed-by=/usr/share/keyrings/oracle-virtualbox.gpg] https://download.virtualbox.org/virtualbox/debian $(lsb_release -cs) contrib" | sudo tee /etc/apt/sources.list.d/virtualbox.list

sudo apt update

sudo apt install -y virtualbox-7.2

VBoxManage -version

wget https://download.virtualbox.org/virtualbox/7.2.8/Oracle_VirtualBox_Extension_Pack-7.2.8.vbox-extpack

sudo VBoxManage extpack install Oracle_VirtualBox_Extension_Pack-7.2.8.vbox-extpack

sudo nano /etc/apt/apt.conf.d/95proxies

curl -fsSL --proxy scheme://username:password@host:port https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg

echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list

sudo apt update

sudo apt install -y vagrant

vagrant -version

sudo apt install -y ansible

ansible --version

mkdir test_vm && cd test_vm

vi Vagrantfile

vagrant up

vagrant ssh

uname -r

mkdir ~/kernel && cd ~/kernel

base=https://kernel.ubuntu.com/mainline/v5.4.220/amd64

wget $base/linux-headers-5.4.220-0504220_5.4.220-0504220.202210261259_all.deb

wget $base/linux-headers-5.4.220-0504220-generic_5.4.220-0504220.202210261259_amd64.deb

wget $base/linux-image-unsigned-5.4.220-0504220-generic_5.4.220-0504220.202210261259_amd64.deb

wget $base/linux-modules-5.4.220-0504220-generic_5.4.220-0504220.202210261259_amd64.deb

sudo dpkg -i *.deb

sudo update-grub

sudo reboot
```
