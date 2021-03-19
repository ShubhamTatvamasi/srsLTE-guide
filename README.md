# srsLTE-guide

config default location `~/.config/srslte/enb.conf`

start eNodeB
```bash
./srsenb
```

run `srsue` as root:
```bash
sudo ./srsue /home/shubham/.config/srslte/ue.conf
```

ping UE from AGW
```bash
ping 192.168.128.14
```
> you will get this IP when you start UE

ping `eth0` IP of AGW from UE:
```bash
sudo ip netns exec ue1 ping 10.0.2.15
```

add default route:
```bash
sudo ip netns exec ue1 ip route add default via 192.168.128.1
sudo ip netns exec ue1 netstat -rnv
sudo ip netns exec ue1 ping 192.168.128.1
```

https://docs.srslte.com/en/latest/app_notes/source/zeromq/source/index.html

---

### not used configs

get all the example config files:
```bash
find . -type f -name "*.example" -exec sudo cp {} /usr/local/share/srslte/ \;
```

install configs:
```bash
srslte_install_configs.sh user
```

change the location of `db_file` file:
```bash
# give full path
vim epc.conf
```

run EPC
```bash
sudo srsepc ~/.config/srslte/epc.conf
```