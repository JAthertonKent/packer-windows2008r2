Install packer

If nesting VirtualBox on a Windows VM running on VMWare Fusion, add
vhv.enable = "TRUE"
to the Windows .vmx file

Lots of good example templates
git@github.com:misheska/basebox-packer.git

Create iso folder at the same level as template folder
Add appropriate Windows ISO
Update template iso_url value
Update iso_checksum
Update iso_checksum_type (md5 didn't work for me)

Otherwise the Windows2012R2 template from basebox-packer repo worked like a charm

Items to note about basebox-packer templates:
- Builds VMware VMDKs as multiple 2GB files.
- Sets autologon for user vagrant (not good for production use)


Install Vagrant
------------------------
gem install vagrant
gem install vagrant-windows
vagrant plugin install vagrant-windows

Must runas "Administrator" on cmd console and Oracle VirtualBox Manager.
vagrant up


Additional details to configure (future)
-------------------------------------------
- Custom VMX template
- Upload to vSphere
- Convert to Template
- Build with paravirtualized Network / SCSI drivers
- Set disk_type_id = 0 for VMware (single vmdk file, thin provisioned)
- Upload to Artifactory
- Windows Updates?
