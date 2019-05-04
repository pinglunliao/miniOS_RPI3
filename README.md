# miniOS_RPI3
Mini OS on Raspberry Pi 3
========================================
主要參考資料為 https://github.com/bztsrc/raspi3-tutorial

Prerequisites
-------------
安裝開發環境
sudo apt install gcc-aarch64-linux-gnu build-essential

安裝模擬環境
sudo apt install qemu-system-arm

使用方式
```sh
qemu-system-aarch64 -M raspi3 -kernel kernel8.img -serial stdio
```

或 (有檔案系統時)

```sh
qemu-system-aarch64 -M raspi3 -kernel kernel8.img -drive file=$(yourimagefile),if=sd,format=raw -serial stdio
```

**-M raspi3**
告訴qemu模擬樹莓派3硬體。

**-kernel kernel8.img**
使用那一個kernel image。

**-drive file=$(yourimagefile),if=sd,format=raw**
使用那個SD card image，可以為標準的rasbian image。

**-serial stdio**

**-serial null -serial stdio**
將UART0重新導向 standard input/output，這樣子才能在qemu看到鍵盤輸入的結果。

**!!!注意!!!** Qemu emulation is rudimentary, only the most common peripherals are emulated! **!!!注意!!!**
