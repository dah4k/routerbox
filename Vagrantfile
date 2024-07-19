# Copyright 2024 dah4k
# SPDX-License-Identifier: EPL-2.0

Vagrant.configure("2") do |config|
    config.vm.box = "freebsd/FreeBSD-13.3-RELEASE"
    config.vm.box_version = "2024.03.02"
    config.vm.hostname = "router"

    config.vm.provider "virtualbox" do |vb|
        vb.gui = false
        vb.linked_clone = true
        vb.memory = 8192
        vb.cpus = 4
    end

    # Disable default sharing current directory
    config.vm.synced_folder ".", "/vagrant", disabled: true

    # https://github.com/opnsense/update#opnsense-bootstrap
    config.vm.provision "Install OPNsense", type: "shell",
        inline: <<-SHELL
            fetch https://raw.githubusercontent.com/opnsense/update/master/src/bootstrap/opnsense-bootstrap.sh.in
            sh ./opnsense-bootstrap.sh.in -r 24.1 -y
        SHELL
end
