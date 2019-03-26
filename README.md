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
# delete orig proto-ncm proto-qmi
```

## Have fun
```
make menuconfig
screen
make V=j
```

## Dont forget
```
luci socat netcat n2n luci-proto-n2n luci-proto-ncm luci-proto-wwan luci-proto-qmi kmod-usb-net-huawei-cdc-ncm
```

## Create WWAN like this
![wwan](https://github.com/mchsk/openwrt-love/raw/master/img/wwan.png "wwan")
