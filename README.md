# OpenWrt

## Prepare your system
```
sudo apt install subversion g++ zlib1g-dev build-essential git python time libncurses5-dev gawk gettext unzip file libssl-dev wget libelf-dev build-essential libncurses5-dev python unzip screen mc
```

## Checkout latest version
```
# go home!
cd ~

git clone https://github.com/openwrt/openwrt.git
cd openwrt
git fetch --all --tags --prune
git checkout tags/v18.06.2

./scripts/feeds update -a
./scripts/feeds install -a
```

## Checkout this repo & copy files
```
# go home!
cd ~

# MAKE THIS REPO PUBLIC (settings/options/down there)

# then clone it
git clone https://github.com/mchsk/openwrt-love.git

# MAKE REPO PRIVATE AGAIN

# delete orig ncm/qmi
rm -rf openwrt/feeds/luci/protocols/luci-proto-ncm/
rm -rf openwrt/feeds/luci/protocols/luci-proto-qmi/

# copy over the files from the openwrt-love over openwrt
rsync -pr ./openwrt-love/package/ ./openwrt/package/
rsync -pr ./openwrt-love/feeds/ ./openwrt/feeds/

# sync the packages
cd openwrt
./scripts/feeds update -a
./scripts/feeds install -a
```

## Config! make menuconfig
```
GENERIC
LuCI/Collections/luci
LuCI/Protocols/luci-proto-n2n
Network/SSH/openssh-sftp-server
Network/netcat
Network/socat

4G
Kernel modules/USB Support/kmod-usb-acm
Kernel modules/USB Support/kmod-usb-net/kmod-usb-net-huawei-cdc-ncm
Kernel modules/USB Support/kmod-usb-ohci
Kernel modules/USB Support/kmod-usb-serial/kmod-usb-serial-wwan
Kernel modules/USB Support/kmod-usb-uhci
Luci/Protocols/luci-proto-3g
Luci/Protocols/luci-proto-wwan(qqan/qmi/ncm)
Network/WWAN/comgt-ncm
Network/3ginfo
Utilities/usb-modeswitch
Utilities/usbutils
```

## Build
```
screen
make
```

## Create WWAN like this
![wwan](https://github.com/mchsk/openwrt-love/raw/master/img/wwan.png "wwan")

