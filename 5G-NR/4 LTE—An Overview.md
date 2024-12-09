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

**Multiantenna schemes**, and in particular single-user MIMO, are an integral part of LTE.

The transmission rank, as well as the exact precoder matrix, can be selected by the network based on channel-status measurements carried out and reported by the terminal, also known as *closed-loop spatial multiplexing*.

LTE release 8 is in theory capable of providing *peak data rates up to 150 Mbit/s in the downlink* using two-layer transmission in *20 MHz and 75 Mbit/s in the uplink*.

## LTE Evolution
![image](https://github.com/user-attachments/assets/43880b49-545a-49ad-8ede-ac7af927a3e8)
- Release 10 (2010):
  - LTE radio-access technology would be fully compliant with the *IMT-Advanced* requirements.
  - backwards compatibility: An earlier-release LTE device should be able to access a carrier supporting LTE release-10 functionality.
  - Introduced enhanced LTE spectrum flexibility through *carrier aggregation*, further extended multiantenna transmission, support for relaying, and improvements around intercell interference coordination in heterogeneous network deployments.
- Release 11 (2012):
  - Radio-interface functionality for *coordinated multipoint (CoMP)* transmission and reception.
  - Carrier-aggregation enhancements, a new control-channel structure (EPDCCH).
- Release 12 (2014):
  - Focused on small cells with features such as dual connectivity, small-cell on/off, and (semi-)dynamic TDD.
  - Introduction of direct device-to-device communication and provisioning of complexity-reduced machine-type communication.
- Release 13 (2015):
  - The start of LTE Advanced Pro.
  - License-assisted access to support unlicensed spectra as a complement to licensed spectra, improved support for machine-type communication, and various enhancements in carrier aggregation, multi-antenna transmission, and deviceto-device communication are some of the highlights.
- Release 14 (2017):
  - Support for vehicle-to-vehicle (V2V) and vehicle-to-everything (V2X) communication.
  - Wide-area broadcast support with a reduced subcarrier spacing.
- Release 15 (2018):
  -Reduced latency through the so-called sTTI feature.

## Spectrum Flexibility
### Carrier Aggregation
- Release 10
  - Multiple component carriers are aggregated and jointly used for transmission to/from a single device.
  - Up to 5 component carriers, possibly each of different bandwidth, can be aggregated in release 10, allowing for transmission bandwidths up to 100 MHz.
  - All component carriers need to have the same duplex scheme.
- Later
  - The number of component carriers possible to aggregate was increased to 32, resulting in a total bandwidth of 640 MHz.
  - A different number of component carriers can be aggregated for the downlink and uplink.
- Release 11
  - Additional flexibility for aggregation of TDD carriers.
  - The same downlink-uplink allocation was required for all the aggregated carriers is **not needed**. -> A TDD-capable device may, similarly to a FDD-capable device, need a duplex filter.
  - The introduction of RF requirements for interband and noncontiguous intraband aggregation.
- Release 12
  - The introduction of RF requirements for interband and noncontiguous intraband aggregation.(FDD-TDD aggregation allows for efficient utilization of an operator’s spectrum assets. It can also be used to improve the uplink coverage of TDD by relying on the possibility for continuous uplink transmission on the FDD carrier.)
- Release 13
  - Increased the number of carriers possible to aggregate from 5 to 32, resulting in a maximum bandwidth of 640 MHz and a theoretical peak data rate around 25 Gbit/s in the downlink.

![image](https://github.com/user-attachments/assets/a0d81f01-35b2-406c-95f4-cddda64c7017)

Component carriers do not have to be contiguous in frequency, which enables exploitation of *fragmented spectra*.Operators with a fragmented spectrum can provide high-data-rate services based on the availability of a wide overall bandwidth even though they do not possess a single wideband spectrum allocation.

## License-Assisted Access
> Using unlicensed spectra as a complement to offer higher data rates and higher capacity in local areas is of interest.
> ![image](https://github.com/user-attachments/assets/6a11ce12-5b42-41be-84d9-32c21acce1a1)

## Multi-Antenna Enhancements
### Extended Multi-Antenna Transmission
-Downlink:  **Release 10**: 8 transmission layers + 3 Gbit/s in 100 MHz -> **Release 13**: 32 carriers + 25 Gbit/s.
-Uplink: **Release 10**: 4 transmission layers + 1.5 Gbit/s in 100 MHz ->

- Release 10: *Reference-signal Structure*: Separated the function of channel estimation and the function of acquiring channel-state information. The aim of this was to better enable novel antenna arrangements and new features such as more elaborate multipoint coordination/transmission in a flexible way.
- Release 13 & 14: Improved support for *massive antenna arrays*, primarily in terms of more extensive feedback of channel-state information.
 ### Multipoint Coordination And Transmission
 - Release 8: Inter-Cell Interference Coordination (ICIC), to control the interference between cells.
 - Release 11: Coordinated Multi-Point (CoMP) transmission/reception.(The support for channel-state feedback for multiple transmission points; Refinement to the reference-signal structure; Enhanced control-channel structure)
 - ![image](https://github.com/user-attachments/assets/e48c2854-ade1-4759-be32-77c8b1d5b44d)
> **Distinguish between (uplink) multipoint coordination and multipoint reception**: uplink CoMP is mainly a *network implementation issue* and has very little impact on the device and very little visibility in the radio-interface specifications.
 ### Enhanced Control Channel Structure
 In release 11, a new complementary control channel structure was introduced to support intercell interference coordination and to exploit the additional flexibility of the new reference-signal structure not only for data transmission, which was the case in release 10, but also for control signaling. The new control-channel structure can thus be seen as a prerequisite for many CoMP schemes, although it is also beneficial for beamforming and frequency-domain interference coordination as well. It is also used to support narrow-band operation for MTC enhancements in releases 12 and 13.

 ## Densification, Small Cells, And Heterogenous Deployments.
 ### Relaying（中继）
Relaying implies that the device communicates with the network via a relay node that is wirelessly connected to a donor cell using the LTE radio-interface technology.
![image](https://github.com/user-attachments/assets/c29c3da9-8671-4c88-9d87-9feaf0f8c59e)
### Heterogenous Deployment
Heterogeneous deployments refer to deployments with a mixture of network nodes with different transmit power and overlapping geographical coverage.
![image](https://github.com/user-attachments/assets/c491ddcd-a92a-46e1-81ca-c851dd55c699)
### Small Cell On/Off
Turning on/off individual cells as a function of the traffic situation to reduce the average intercell interference and reduce power consumption.
### Dual Connectivity
Dual connectivity implies a device is simultaneously connected to two cells.
- User-plane aggregation, where the device is receiving data transmission from multiple sites.
- Separation of control and user planes.
- uplink-downlink separation where downlink transmissions originate from a different node than the uplink reception node.
- ![image](https://github.com/user-attachments/assets/c1c9b6bb-3e20-4089-b626-e1957791c81b)
### Dynamic TDD
- Unpaired spectrum allocations being more common in higher-frequency bands not suitable for wide-area coverage.
- Many problematic interference scenarios in wide-area TDD networks are not present with below-rooftop deployments of small nodes.
> In dynamic TDD, the network can dynamically use resources for either uplink or downlink transmissions to match the instantaneous traffic situation, which leads to an improvement of the end-user performance compared to the conventional static split of resources between uplink and downlink.
### WLAN Interworking
The device may select Wi-Fi even if staying on LTE would provide a better user experience. One example of such a situation is when the Wi-Fi network is heavily loaded while the LTE network enjoys a light load. Release 12 therefore introduced means for the network to assist the device in the selection procedure.
Basically, the network configures a signal-strength threshold controlling when the device should select LTE or Wi-Fi.

## Device Enhancements
Network deployments therefore need to be based on the minimum requirements. 
Defining performance requirements for more advanced receiver types to some extent alleviates this as the minimum performance of a device equipped with an advanced receiver is known.

*Network-assisted Interference Cancellation (NAICS)*
##   New Scenarios
### Device-To-Device Communication
- In coverage as well as out-of-coverage communication for public safety.
- In coverage discovery of neighboring devices for commercial use cases.
- ![image](https://github.com/user-attachments/assets/43bc2b78-5e61-495c-bc58-265466f4f2ab)
### Machine-Type Communication(MTC)
- Massive MTC
  - These devices typically have to be of very low cost and have very low energy consumption, enabling very long battery life.
  - The amount of data generated by each device is normally very small and very low latency is not a critical requirement.
- URLLC
  - Applications such as traffic safety/control or wireless connectivity for industrial processes, and in general scenarios where very high reliability and availability is required, combined with low latency.
- Narrow-band Internet-of-Things (NB-IoT)
  - It targets even lower cost and data rates than category-M1, 250 kbit/s or less, in a bandwidth of 180 kHz, and even further enhanced coverage.
### Latency Reduction — STTI
- The target with this feature is to provide very low latency for use cases where this is important, for example factory automation.
### V2V And V2X
- Intelligent transportation systems (ITSs) refer to services to improve traffic safety and increase efficiency.
  ![image](https://github.com/user-attachments/assets/ee2658ac-bcf2-4a4e-b5db-f2dcb7ca5c80)
## Aerials
- The work on aerials in release 15 covers communication via a drone acting as a relay to provide cellular coverage in an otherwise noncovered area, but also remote control of drones for various industrial and commercial applications.
