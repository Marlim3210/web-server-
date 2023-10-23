# DNS SERVER
Menginstall DNS Server untuk kebutuhan Web Server

## Cara Instalasi
jalankan perintah berikut untuk _install bind9_

<code>apt install bind9</code>

## Konfigurasi Network Interface
Sebelumnya kita konfigurasi IP Address secara Static, Resolv.conf dan hosts seperti dibawah ini.

<code>nano /etc/netplan/00-installer-config.yaml</code>

# Konfigurasi interface

<code>This is the network config written by 'subiquity'
network:
  ethernets:
    enp0s3:
      dhcp4: false
      addresses: [192.168.20.10/24]
      gateway4: 192.168.20.1
      nameservers:
        search: [aspal.com]
        addresses: [192.168.20.10, 192.168.20.1]
  version: 2</code>

# Konfigurasi Resolv.conf
<code>  nano /etc/resolv.conf

operation for /etc/resolv.conf.
nameserver 192.168.20.10
nameserver 192.168.20.1
options edns0
search aspal.com</code>