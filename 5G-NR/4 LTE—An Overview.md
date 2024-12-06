# LTE—An Overview
## LTE RELEASE 8—BASIC RADIO ACCESS
Important Requirement：**Spectrum Flexibility**

Support of both paired and unpaired spectrum using **Frequency-Division Duplex (FDD)** and **Time-Division Duplex (TDD)**, respectively,
with a common design, albeit two different frame structures.

Basic Transmission Scheme: OFDM
- Robustness to time dispersion and ease of exploiting both the time and frequency domain.
- It also allows for reasonable receiver complexity also in combination with spatial multiplexing (MIMO) which is an inherent part of LTE.
- For the uplink, the LTE design settled for a scheme with a low peak-toaverage ratio to provide a high power-amplifier efficiency.
   **DFT-precoded OFDM**离散傅里叶变换扩展正交频分复用(drawback: larger complexity on the receiver side)

In the **time domain**, LTE organizes transmissions into 10-ms frames, each consisting of ten 1-ms subframes. The subframe duration of 1 ms, which corresponds
to 14 OFDM symbols, is the smallest schedulable unit in LTE.

**Cell-specific reference signals** is a cornerstone in LTE.
CRS信号：（1）可被用于下行物理信道的信道估计；（2）可被UE用来获取CSI；（3）基于小区特定的参考信号的终端测量可用作决定小区选择和切换的基础。

Data transmission in LTE is primarily scheduled on a dynamic basis in both uplink and downlink.

The scheduling decisions are provided to the device through the **Physical Downlink Control Channel (PDCCH)**.
在5G NR中，控制信道仅包括PDCCH（Physical Downlink Control Channel），负责物理层各种关键控制信息的传递
