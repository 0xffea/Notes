
Rebased patch can be found at
https://github.com/0xffea/illumos-gate/tree/brand-lx

Configure a new linux branded zone:
```shell
zonecfg -z lx-zone "create -t SUNWlx; set zonepath=/export/home/lx-zone; set autoboot=true"
```

Install the zone:
```shell
zoneadm -z lx-zone install -d centos_fs.tar.bzip2
```
