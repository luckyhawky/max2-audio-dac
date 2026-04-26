# R2R 24-bit Stereo Audio DAC for bluetooth
![Platform](https://img.shields.io/badge/platform-MAX--II-red)
![GitHub](https://img.shields.io/github/license/dilshan/max2-audio-dac)

拥抱无线时代的 Hi-Fi 升级：引入 I2S 蓝牙模块

在现代桌面音频系统中，纯有线的连接方式虽然复古，但确实牺牲了日常使用的便利性。为这个 R2R DAC 增加一个带有 I2S（IIS）数字输出的蓝牙接收模块（例如基于高通 QCC5125 或 CSR8675 芯片的模块），绝对是一个能让这个开源作品“焕发新生”的绝佳升级方案。

为什么一定要强调 I2S 输出？市面上普通的廉价蓝牙模块通常只提供模拟音频输出（AUX），其内部自带的低端解码芯片底噪大、失真高，如果用它，就会完全糟蹋了我们费尽心血优化的 R2R 架构和双电源运放。而带有 I2S 接口的高级蓝牙模块，能在接收到手机推送的 LDAC、aptX HD 或 AAC 等高清蓝牙音频后，跳过内部劣质解码，直接输出原汁原味的纯数字 PCM 信号（包含时钟 BCLK、帧同步 WCLK 和数据 DIN）。

在硬件改造上，这种结合非常顺滑。你只需要将蓝牙模块的 I2S 引脚直接接入 EPM240 CPLD 原本预留的输入端。系统工作时，蓝牙模块作为主机（Master）提供纯净的音频时钟，CPLD 则专心负责将接收到的串行 I2S 数据打散重组，转换为 24 路并行数据去精确驱动后端的电阻网络。

只需增加几十块钱的物料成本，你就能彻底摆脱线缆束缚，直接躺在沙发上用手机里的 Apple Music 或流媒体软件推送无损音乐。这不仅是一次极具性价比的升级，更是将经典的 R2R “模拟味”与现代智能设备的“极致便利”完美融合到了你的专属解码器中！


![MAX-II DAC Module](https://raw.githubusercontent.com/wiki/dilshan/max2-audio-dac/DSCN1155P-720p.JPG)

This is a 24-bit stereo DAC, which is specifically built for Raspberry Pi boards. This R-2R ladder DAC is developing around Intel / Altera *EPM240T100C5N* CPLD.

DAC which described in this repo can directly connect with the I2S interface of Raspberry Pi boards. The recommended supply voltage for this DAC is 5V to 8V.

The *MCP602* opamp of this module is capable to drive headphone directly. An external AF power amplifier must pair with this module to obtain a higher output power.

This repository contains all the files and binaries to build DAC, which including *Intel Quartus* Project files, Raspberry Pi Device Tree Overlays, etc.

This is certified open-source hardware project. All the content of this project are distributed under the terms of the following license:

-   Hardware License: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
-   Software License: [MIT](https://github.com/dilshan/max2-audio-dac/blob/master/LICENSE)
-   [Documentation](https://github.com/dilshan/max2-audio-dac/wiki) License: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

[![OSHW-LK000006](https://raw.githubusercontent.com/dilshan/max2-audio-dac/master/OSHW_LK000006.png)](https://certification.oshwa.org/lk000006.html)
