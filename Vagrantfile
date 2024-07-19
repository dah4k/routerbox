# Copyright 2024 dah4k
# SPDX-License-Identifier: EPL-2.0

Vagrant.configure("2") do |config|
    config.vm.box = "freebsd/FreeBSD-14.1-RELEASE"
    config.vm.box_version = "2024.05.31"
    config.vm.hostname = "router"

    config.vm.provider "virtualbox" do |vb|
        vb.gui = false
        vb.linked_clone = true
        vb.memory = 8192
        vb.cpus = 4
    end

    # Disable default sharing current directory
    config.vm.synced_folder ".", "/vagrant", disabled: true

end
