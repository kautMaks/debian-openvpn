# debian-openvpn

This repository provides openvpn debianized source package for Debian.

Source repository - https://salsa.debian.org/debian/openvpn

## Install build requirements:

```
apt-get -qq update && apt-get -y install build-essential debhelper devscripts dpkg-dev fakeroot git iproute2 liblz4-dev liblzo2-dev libpam0g-dev libpkcs11-helper1-dev libssl-dev libsystemd-dev net-tools pkg-config 
```

## Clone this repo to your build server:

```
cd /root
git clone https://github.com/kautMaks/debian-openvpn
```

## Get openvpn sources:

```
wget https://swupdate.openvpn.org/community/releases/openvpn-2.4.8.tar.gz
tar --transform 's,openvpn-2.4.8,debian-openvpn,' -xvf openvpn-2.4.8.tar.gz
cd  debian-openvpn/
```

## Build openvpn with enabled tests:

```
debuild -us -uc -b
```

## Build openvpn with disabled tests:

```
DEB_BUILD_OPTIONS=nocheck debuild -us -uc -b
```
