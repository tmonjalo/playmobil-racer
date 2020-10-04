# Playmobil Racer

https://rcracers.playmobil.com

The Playmobil toy car is remote controlled with **Bluetooth Low Energy** (BLE).

This repository includes:
- [reverse-engineered protocol](protocol.md)
- [python module](pmrc.py)

## Status

The protocol has been analyzed using the Android application, thanks to the HCI log.

The python module is working on Linux by using bluepy.

## Troubleshooting

### Permission Denied

When scanning BLE devices, some root capabilities are required:

> bluepy.btle.BTLEManagementError: Failed to execute management command 'le on' (code: 20, error: Permission Denied)

The solutions are either to run as root (`sudo`) or to grant capabilities to `bluepy-helper`:
```
find /usr -name 'bluepy-helper' -exec sudo setcap 'cap_net_raw,cap_net_admin+eip' '{}' \;
```
