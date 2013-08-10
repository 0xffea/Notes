
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

Enable debug output:
```shell
echo "lx_debug/W 1" | mdb -kw
```

List dtrace probes:
```shell
dtrace -P lxsyscall -l
```

Halt zone:
```shell
zoneadm -z lx-zone halt
```

- [] klogd runs wild in syslog
- [] proc not mounted (top, ps not working)
