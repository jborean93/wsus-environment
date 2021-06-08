# WSUS Test Environment

Creates a test environment to use for Windows Update testing against a WSUS server.


## Requirements

* Vagrant
* QEMU/Libvirt
* Ansible
  * `ansible.windows`
  * `community.windows`
  * `chocolatey.chocolatey`
  * `community.general` - only for the yaml callback in `ansible.cfg`


## Environment details

Sets up the following hosts

* `DC` - Domain controller
* `WSUS-SERVER` - The WSUS server
* `APP` - The app server that is configured to talk to `WSUS-SERVER`

All these hosts are running on Windows Server 2019.
The WSUS server is configured with the following settings:

* `Classifications`: Everything except `Drivers` and `Driver Sets`
* `Products`: All the `Windows Server 2019*` products
* The initial synchronisation with Microsoft Update has been completed
* No updates have been approved or downloaded

