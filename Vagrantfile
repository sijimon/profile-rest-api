Vagrant.configure("2") do |config|
  config.vm.box = "generic/ubuntu1804"
  config.vm.synced_folder ".", "/vagrant"
  config.vm.network "forwarded_port", guest: 8000, host: 8000
  config.vm.provision "shell", inline: <<-SHELL
    systemctl disable apt-daily.service
    systemctl disable apt-daily.timer
    sudo apt-get update
    sudo apt-get install -y python3-venv zip
    touch /home/vagrant/.bash_aliases
    if ! grep -q PYTHON_ALIAS_ADDED /home/vagrant/.bash_aliases; then
      echo "# PYTHON_ALIAS_ADDED" >> /home/vagrant/.bash_aliases
      echo "alias python='python3'" >> /home/vagrant/.bash_aliases
    fi
  SHELL
end