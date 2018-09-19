# c-sky

1. buy a board at taobao 

```
https://item.taobao.com/item.htm?spm=a1z10.1-c.w4004-13250088290.6.4b1f9628jKW8o8&id=556322544984
```

2. download img


3. dd to usb

```
sudo dd if=usb.img of=/dev/sdb bs=8192;sync;
```

4. run

```
sudo minicom -D /dev/ttyUSB0
```






bianyi

```
#pacman -S build-essential git lzip ncurses-dev minicom
```
```
git clone https://github.com/c-sky/buildroot.git
cd buildroot
```

uart

```
make csky_gx6605s_defconfig
```

or hdmi

```
make csky_gx6605s_fbcon_defconfig
```

make
```
make
```




driver:

1. net

rtl8152 usb
```
$udhcpc -i eth0
```

2. wifi
mt7601u WIFI linux
```
/* 加载驱动 */
$modprobe mt7601u
/* 设置连接 AP 密码 */
$wpa_passphrase qa_test3_d300 12345678 >> /etc/wpa_supplicant.conf
/* 启动wifi连接 */
$wpa_supplicant -Dnl80211 -iwlan0 -c /etc/wpa_supplicant.conf -B
/* 获取 DHCP */
$udhcpc -i wlan0
```
