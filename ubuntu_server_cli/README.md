# Ubunbu Server Config

## Troubleshooting

### Locales

```
sudo apt install locales
sudo dpkr-reconfigure locales
```

### Wait for network to be configured upon boot
> A start job is running for wait for network to be Configured

```shell
cd /etc/systemd/system/network-online.target.wants/
nano systemd-networkd-wait-online.service
```

在`[service]`下增加一行
```TimeoutStartSec=1sec```

