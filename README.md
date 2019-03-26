# OpenWrt

## Prepare your system
```
sudo apt install subversion g++ zlib1g-dev build-essential git python time libncurses5-dev gawk gettext unzip file libssl-dev wget libelf-dev build-essential libncurses5-dev python unzip screen
```

## Checkout latest version
```
git clone https://github.com/openwrt/openwrt.git
git fetch --all --tags --prune
git checkout tags/v18.06.2
cd openwrt
./scripts/feeds update -a
./scripts/feeds install -a
```

## Checkout this repo & copy files
```
git clone https://github.com/mchsk/openwrt-love.git
```

## Have fun
```
make menuconfig
screen
make V=j
```
