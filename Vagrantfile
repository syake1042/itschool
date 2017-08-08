Vagrant.configure("2") do |config|
 config.vm.define "web1" do |web1|
  web1.vm.box = "centos/7"
  web1.vm.network "private_network", ip: "192.168.33.10"
   web1.vm.provision "shell", inline: <<-SHELL
     yum update -y
     yum install httpd -y
   SHELL
 end
 config.vm.define "web2" do |web2|
  web2.vm.box = "centos/7"
  web2.vm.network "private_network", ip: "192.168.33.11"
   web2.vm.provision "shell", inline: <<-SHELL
     yum update -y
     yum install httpd -y
   SHELL
 end
 config.vm.define "nginx" do |nginx|
  nginx.vm.box = "centos/7"
  nginx.vm.network "private_network", ip: "192.168.33.12"
  nginx.vm.provision "shell", inline: <<-SHELL
   rpm -ivh http://nginx.org/packages/centos/7/noarch/RPMS/nginx-release-centos-7-0.el7.ngx.noarch.rpm 
   yum install nginx -y
   yum clean all
   yum update -y
 SHELL
 end
end
