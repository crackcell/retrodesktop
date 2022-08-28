# NsCDE Setup

## Autostart

- NsCDE在`Init.fvwmconf`中会调用`~/.config/autostart/*.desktop`来启动程序
- 可以从`/usr/share/applications/`中链接desktop文件过来

## Troubleshooting

### nm-applet提示权限问题
> Authentication required. System policy prevents WiFi scans

在`/etc/polkit-1/localauthority/50-local.d`下创建一个`allow_nm.pkla`，内容如下：
```
[Allow Wifi Scan]
Identity=unix-user:*
Action=org.freedesktop.NetworkManager.wifi.scan;org.freedesktop.NetworkManager.enable-disable-wifi;org.freedesktop.NetworkManager.settings.modify.own;org.freedesktop.NetworkManager.settings.modify.system;org.freedesktop.NetworkManager.network-control
ResultAny=yes
ResultInactive=yes
ResultActive=yes
```
