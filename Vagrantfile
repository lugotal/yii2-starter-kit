# Please see the online documentation at
# https://docs.vagrantup.com.

# OPTIONS
require 'yaml'
options = YAML.load_file File.join(File.dirname(__FILE__), '/vagrant/vagrant.yaml')
domains = [
    "yii2-starter-kit.localhost",
    "backend.yii2-starter-kit.localhost",
    "storage.yii2-starter-kit.localhost"
]
packages = [
    "php7.4",
    "php7.4-cli",
    "php7.4-common",
    "php7.4-curl",
    "php7.4-fpm",
    "php7.4-gd",
    "php7.4-intl",
    "php7.4-json",
    "php7.4-mysql",
    "php7.4-opcache",
    "php7.4-readline",
    "php7.4-mbstring",
    "php7.4-dom",
    "php-xdebug",
    "nginx",
    "mysql-server-5.7",
    "git",
    "zip",
    "php7.4-zip"
]

Vagrant.configure(2) do |config|
  config.vm.post_up_message = "Done! Now you can access site at http://yii2-starter-kit.localhost"
  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = options['vm']['memory']
    vb.cpus = options['vm']['cpus']
    vb.name = options['vm']['name']
  end

  config.vm.define options['vm']['name'] {}

  config.vm.box = "ubuntu/bionic64"

  # Make sure we're using UTF-8 to avoid Apt issues
  ENV['LC_ALL']="C.UTF-8"

  config.vm.hostname = domains[0]
  config.vm.network "private_network", ip: options['network']['ip']
  config.vm.synced_folder "./", "/var/www", id: "vagrant-root", :nfs => false, owner: "www-data", group: "www-data"

  config.vm.provision :hostmanager
  config.hostmanager.enabled            = true
  config.hostmanager.manage_host        = true
  config.hostmanager.ignore_private_ip  = false
  config.hostmanager.include_offline    = true
  config.hostmanager.aliases            = domains

  # fix "stdin: is not a tty"
  config.vm.provision "fix-no-tty", type: "shell" do |s|
    s.privileged = false
    s.inline = "sudo sed -i '/tty/!s/mesg n/tty -s \\&\\& mesg n/' /root/.profile"
  end

  config.vm.provision "shell", path: "./vagrant/vagrant.sh", args: [
    packages.join(" "),
    options['github']['token'],
    options['system']['swapsize'],
    options['system']['timezone']
  ]

  config.vm.provision "shell", inline: "service nginx restart", run: "always"
end
