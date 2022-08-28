# Ubunbu Server Config

## Install base system
```shell
sudo apt install -y locales \
  network-manager-gnome network-manager-openvpn \
  thunar terminator \
  git build-essential nano
```

## Troubleshooting

### Locales

```
sudo apt install locales
sudo dpkg-reconfigure locales
```

### Wait for network to be configured upon boot
> A start job is running for wait for network to be Configured

```shell
cd /etc/systemd/system/network-online.target.wants/
nano systemd-networkd-wait-online.service
```

在`[service]`下增加一行
```TimeoutStartSec=1sec```

