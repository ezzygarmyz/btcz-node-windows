# btcz-node-windows

WSL2 : Ubuntu 24.04 LTS

```
sudo apt update && sudo apt upgrade -y
```
### Requirements :
```
sudo apt install build-essential libtool autotools-dev automake pkg-config bsdmainutils cmake curl git mingw-w64 -y
```
### Build

```
git clone --single-branch --branch 2.0.9-dev6 https://github.com/MarkLTZ/bitcoinz.git

cd bitcoinz/depends

sudo make HOST=x86_64-w64-mingw32

cd ..

sudo ./autogen.sh

sudo CONFIG_SITE=$PWD/depends/x86_64-w64-mingw32/share/config.site ./configure LDFLAGS="-lbcrypt"

sudo make -j$(nproc)

```
