Vagrant.configure("2") do |config|

  config.vm.define "ubuntu-cis-hardened" do |ubuntu|
    ubuntu.vm.box = "ubuntu-gui"
    ubuntu.vm.hostname = "ubuntu-cis"
    ubuntu.vm.network "private_network", ip: "192.168.56.10", type: "static"
    
    ubuntu.vm.provider "virtualbox" do |vb|
      vb.name = "ubuntu-cis-hardened"
      vb.memory = "3072"
      vb.cpus = 2
      vb.gui = true
    end
  end

  config.vm.define "windows-cis-hardened" do |win|
    # ИМЕНА ПО АНАЛОГИИ С UBUNTU
    win.vm.box = "windows-gui"           # ← имя box'а
    win.vm.hostname = "windows-cis"      # ← имя хоста внутри VM
  
    # Host-only сеть
    win.vm.network "private_network", ip: "192.168.56.20", type: "static"
  
    win.vm.provider "virtualbox" do |vb|
      vb.name = "windows-cis-hardened"
      vb.memory = "4096"
      vb.cpus = 2
      vb.gui = true
    end

    # Настройки WinRM
    win.vm.communicator = "winrm"
    win.winrm.username = "vagrant"
    win.winrm.password = "vagrant"
    win.winrm.timeout = 60
  end
end