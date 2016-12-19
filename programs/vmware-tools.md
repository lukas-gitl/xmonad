# Install VMware Tools
> [Reference](https://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1022525)

We are using the iso coming from VMware as it includes the lastest VMware Tools. Most importantly it includes multi screen support. Discussion can be found [here](http://superuser.com/questions/270112/open-vm-tools-vs-vmware-tools).
## a) Mount CD
* Add a CD Drive to the VM
* Use `Install VM Tools`

## b) Install VMware
Download [scripts/update-vm-tools](scripts/update-vmware-tools) and run it with 
```shell
. update-vm-tools
```
To confirm the installation worked correctly run
```shell
vmware-toolbox-cmd -v
```
When done feel free to remove the cd drive again in VMware.

## c) Configure Autostart
> [Reference](http://askubuntu.com/questions/777839/fresh-ubuntu-16-04-install-broken-vmware-tools#answer-777922)

To enable vm tools you need to run `/usr/bin/vmware-user`.

To enable this as autostart, copy `config/.xmonad/autostart` to `~/.xmonad/autostart`. The `autostart` file is safe to keep around, as it will only fire when VMware Tools are installed.