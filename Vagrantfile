# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Configura o box (imagem) do Ubuntu 21.04
  config.vm.box = "ubuntu/21.04"

  # Configura a quantidade de memória RAM e processadores
  config.vm.provider "virtualbox" do |vb|
    vb.memory = 2048 # 2GB de RAM
    vb.cpus = 2      # 2 processadores
  end

  # Script de provisionamento com shell
  config.vm.provision "shell", inline: <<-SHELL
    # Atualiza a lista de pacotes
    sudo apt-get update

    # Instalação do Node.js 14.x
    curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
    sudo apt-get install -y nodejs

    # Instalação do Docker
    sudo apt-get install -y docker.io

    # Adiciona o usuário vagrant ao grupo docker para executar comandos sem sudo
    sudo usermod -aG docker vagrant
  SHELL
end
