Updated driver for rtl88x2bu wifi adaptors based on rtl88x2BU_WiFi_linux_v5.2.4.4_26334.20180126_COEX20171012-5044.

Build confirmed on `Linux version 4.16.0-2-amd64 (debian-kernel@lists.debian.org) (gcc version 7.3.0 (Debian 7.3.0-19)) #1 SMP Debian 4.16.12-1 (2018-05-27)`

See http://www.wolfteck.com/2018/02/22/wsky_1200mbps_wireless_usb_wifi_adapter/ for all the hows and whys around the updates.

# Fair warning...

Thanks to [MaxG87](https://github.com/cilynx/rtl88x2BU_WiFi_linux_v5.2.4.4_25643.20171212_COEX20171012-5044/issues/3), no more [scary provenance warning](https://github.com/cilynx/rtl88x2BU_WiFi_linux_v5.2.4.4_25643.20171212_COEX20171012-5044#fair-warning)! W00t.

You can find the original source for this driver on [D-Link's download page for the DWA-182 Rev D](https://support.dlink.com/ProductInfo.aspx?m=DWA-182).

# DKMS installation

```bash
cd rtl88x2BU_WiFi_linux_v5.2.4.4_25643.20171212_COEX20171012-5044
VER=$(cat ./version)
sudo rsync -rvhP ./ /usr/src/rtl88x2bu-${VER}
sudo dkms add -m rtl88x2bu -v ${VER}
sudo dkms build -m rtl88x2bu -v ${VER}
sudo dkms install -m rtl88x2bu -v ${VER}
sudo modprobe 88x2bu
```
