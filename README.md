<h1>WPI i.MX Linux Yocto Project BSP 5.15.71_2.2.0 Release for Desktop</h1>

此資源庫是基於 [NXP i.MX Linux BSP Software \[meta-nxp-desktop\]](https://github.com/nxp-imx/meta-nxp-desktop) 建立而成，用於提供 WPI 客製化的 Yocto Layer。

下方列表為 WPI 此次版本，已測試過的開發板。

* [WPI OP-Killer](https://www.wpgdadatong.com/tw/solution/detail/36783) (opkiller)

若是想要編譯 NXP 的開發板亦可使用此 BSP，將下方 MACHINE 改設為 NXP 提供的參數即可，
詳情請參考 [meta-nxp-desktop](https://github.com/nxp-imx/meta-nxp-desktop) 了解更多內容。

## Quick Start Guide

1. <a>安裝 WPI i.MX Linux BSP repo</a>

```!
$ repo init -u https://github.com/WPI-ATU/wpi-manifest.git -b imx-linux-kirkstone -m imx-5.15.71-2.2.0_desktop.xml
```

2. 下載 <a>i.MX Yocto Layers</a>

```!
$ repo sync
```

* 如果 ``repo init`` 有問題，請移除 ``.repo`` 並重新執行 ``repo init``。

3. 建立 <a>i.MX 的編譯環境</a>

```
$ [MACHINE=<machine>] DISTRO=imx-desktop-xwayland source ./imx-setup-desktop.sh -b <build folder>
```

* \<machine\> - 開發板名稱，OP-Killer 請設為 ``opkiller``
* \<build folder\> - 建立的資料夾名稱

## 建立 Images

```!
$ DISTRO=imx-desktop-xwayland MACHINE=imx8mpevk source imx-setup-desktop.sh -b build-desktop
$ bitbake imx-image-desktop
```

## ATU Support

* [NXP i.MX8 大大通技術索引](https://hackmd.io/@WPI-ATU-TW1/Bk3zvW0Ts/https%3A%2F%2Fhackmd.io%2FXC9STgFjSs6_vadDkO0YSA%3Fboth?utm_source=preview-mode&utm_medium=rec)

<img src="https://hackmd.io/_uploads/Hy773SVvn.png"  width="200" height="200">

如果你有任何需求，請聯絡 WPI 的 [TW ATU](mailto:wpi.atu.github@wpi-group.com) 團隊
