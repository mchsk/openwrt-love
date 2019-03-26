# OpenWrt

## Prepare your system
```
sudo apt install subversion g++ zlib1g-dev build-essential git python time libncurses5-dev gawk gettext unzip file libssl-dev wget libelf-dev build-essential libncurses5-dev python unzip  
```

## Prepare latest OpenWrt data - check the tag!
```
git clone https://github.com/openwrt/openwrt.git
git fetch --all --tags --prune
git checkout tags/v18.06.2
cd openwrt
./scripts/feeds update -a
./scripts/feeds install -a
```

```
git clone https://github.com/openwrt/openwrt.git
git fetch --all --tags --prune
git checkout tags/v18.06.2
```
