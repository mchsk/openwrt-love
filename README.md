# OpenWrt

## Prepare your system
```
sudo apt install subversion g++ zlib1g-dev build-essential git python time libncurses5-dev gawk gettext unzip file libssl-dev wget libelf-dev build-essential libncurses5-dev python unzip screen
```

## Checkout latest version
```
git clone https://github.com/openwrt/openwrt.git
cd openwrt
git fetch --all --tags --prune
git checkout tags/v18.06.2

./scripts/feeds update -a
./scripts/feeds install -a
```

## Checkout this repo & copy files
```
# MAKRE REPO PUBLIC
git clone https://github.com/mchsk/openwrt-love.git
# MAKRE REPO PRIVATE

# delete orig openwrt/feeds/luci/protocols/proto-wwan,proto-ncm,proto-qmi
# copy there tfe files from openwrt-love over openwrt

# in orig openwrt run ./scripts/feeds update -a + ./scripts/feeds install -a
```

## Config! make menuconfig
```
GENERIC
Administration/htop
LuCI/Collections/luci
LuCI/Protocols/luci-proto-n2n
Network/SSH/openssh-sftp-server
Network/netcat
Network/socat (SSL support)

4G
Kernel modules/USB Support/kmod-usb-net/kmod-usb-net-huawei-cdc-ncm
Kernel modules/USB Support/kmod-usb-serial/kmod-usb-serial-wwan
Kernel modules/USB Support/kmod-usb-acm
Kernel modules/USB Support/kmod-usb-ohci
Kernel modules/USB Support/kmod-usb-uhci
Luci/Protocols/luci-proto-3g
Luci/Protocols/luci-proto-wwan(qqan/qmi/ncm)
Network/WWAN/comgt-ncm
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

