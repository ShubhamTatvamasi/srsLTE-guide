# srsLTE-guide

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

eNodeB config:
```bash
vim ~/.config/srslte/enb.conf
```
