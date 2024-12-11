![image](https://github.com/user-attachments/assets/21348c50-ff52-4c39-af03-be94838d0e50)

Compared to LTE, NR provides many benefits. Some of the main ones are:
- Exploitation of much higher-frequency bands as a mean to obtain additional spectra to support very wide transmission bandwidths and the associated high data rates;
- Ultra-lean design to enhance network energy performance and reduce interference;
- Forward compatibility to prepare for future, yet unknown, use cases and technologies;
- Low latency to improve performance and enable new use cases;
- A beam-centric design enabling extensive usage of beamforming and a massive number of antenna elements not only for data transmission (which to some extent is possible in LTE) but also for control-plane procedures such as
initial access.
## HIGHER-FREQUENCY OPERATION AND SPECTRUM FLEXIBILITY
One key feature of NR is a substantial expansion in terms of the range of spectra in which the radio-access technology can be deployed. Unlike LTE, where support for licensed spectra at 3.5 GHz and unlicensed spectra at 5 GHz are just being introduced, NR supports licensed-spectrum operation from **below 1 GHz up to 52.6 GHz** already from its first release.
## ULTRA-LEAN DESIGN
An issue with current mobile-communication technologies is the amount of transmissions carried by network nodes regardless of the amount of user traffic. Such signals, sometimes referred to as “always-on” signals.

The always-on transmissions have two negative impacts:
- They impose an upper limit on the achievable network energy performance;
- They cause interference to other cells, thereby reducing the achievable data rates.
The *ultra-lean design* principle aims at minimizing the always-on transmissions, thereby enabling higher network energy performance and higher achievable data rates.

3GPP agreed on some basic design principles related to NR forward compatibility:
- Maximizing the amount of time and frequency resources that can be flexibly utilized or that can be left blank without causing backward compatibility issues in the future;
- Minimizing transmission of always-on signals;
- Confining signals and channels for physical layer functionalities within a configurable/allocable time/frequency resource.(*as much as possible, avoid having transmissions on time/frequency resources fixed by the specification. In this way one retains flexibility for the future, allowing for later introduction of new types of transmissions with limited constraints from legacy signals and channels.*)

## TRANSMISSION SCHEME, BANDWIDTH PARTS, AND FRAME STRUCTURE
- NR uses conventional, that is, **non-DFT-precoded OFDM**, as the baseline uplink transmission scheme due to the simpler receiver structures in combination with spatial multiplexing and an overall desire to have the same transmission scheme in both uplink and downlink.
- DFT-precoding can be used as a complement in the uplink, namely to enable high power-amplifier efficiency on the device side by reducing the *cubic metric*. Cubic metric is a measure of the amount of additional power back-off needed for a certain signal waveform.
- NR supports a flexible OFDM numerology with subcarrier spacings ranging from 15 kHz up to 240 kHz with a proportional change in cyclic prefix duration.
  ![image](https://github.com/user-attachments/assets/bea36552-4936-440a-8349-5a19eda7b068)
- NR allows for *device-side receiver-bandwidth adaptation* as a means to reduce the device energy consumption.
- NR supports a more efficient approach to low latency by allowing for transmission over a fraction of a slot, sometimes referred to as “mini-slot” transmission. Such transmissions can also preempt an already ongoing slot-based transmission to another device, allowing for immediate transmission of data requiring very low latency.
  ![image](https://github.com/user-attachments/assets/0febff4b-d681-415d-8b24-720d91afe484)
- Unlike LTE, NR does not include cell-specific reference signals but solely relies on user-specific demodulation reference signals for channel estimation.
## BEAM-CENTRIC DESIGN AND MULTI-ANTENNA TRANSMISSION
- Support for a for a large number of steerable antenna elements for both transmission and reception is a key feature of NR. At higher-frequency bands, the large number of antenna elements are primarily used for beamforming to extend coverage, while at lower-frequency sometimes referred to as massive MIMO, and interference avoidance by spatial separation.bands they enable full-dimensional MIMO, sometimes referred to as massive MIMO, and interference avoidance by spatial separation.
- Analog beamforming results in the constraint that a receive or transmit beam can only be formed in one direction at a given time instant and requires beam-sweeping where the same signal is repeated in multiple OFDM symbols but in different transmit beams.
![image](https://github.com/user-attachments/assets/a8b16cc4-15f2-478d-bbdf-c4ebf51d5cf8)

## Duplex Schemes ##
![image](https://github.com/user-attachments/assets/6883fef1-3cba-4934-89ff-75f94876176f)
- For lower-frequency bands, allocations are often paired, implying frequencydivision duplex (FDD). At higher-frequency bands, unpaired spectrum allocations are increasingly common, calling for time-division duplex (TDD).
- NR can operate in both paired and unpaired spectra using **one common frame** structure. The basic NR frame structure is designed such that it can support both half-duplex and full-duplex operation.
- In such denser deployments with smaller cell sizes, the per-cell traffic variations are more rapid compared to large-cell deployments with a large number of active devices per cell. To address such scenarios, dynamic TDD, that is, the possibility for dynamic assignment and reassignment of time-domain resources between the downlink and uplink transmission directions, is a key NR technology component.

## Low Latency Support
- One example is the use of “front-loaded” reference signals and control signaling.
- The requirements on the device (and network) processing times are tightened significantly in NR compared to LTE.
- The higher-layer protocols MAC and RLC have also been designed with low latency in mind with header structures chosen to enable processing without knowing the amount of data to transmit.

## SCHEDULING AND DATA TRANSMISSION
- Instead of trying to combat these variations, they can be exploited through *channel-dependent scheduling* where the time-frequency resources are dynamically shared between users.
## Control Channels
- Downlink control channels are known as PDCCHs (physical downlink control channels). One major difference compared to LTE is the more flexible timefrequency structure of downlink control channels where PDCCHs are transmitted in one or more control resource sets (CORESETs). Another major difference compared to LTE is the support for beamforming of the control channels, which has required a different reference signal design with each control channel having its own dedicated reference signal.
- Uplink control information, such as hybrid-ARQ acknowledgments, channelstate feedback for multi-antenna operation, and scheduling request for uplink data awaiting transmission, are transmitted using the physical uplink control channel (PUCCH).
- For the physical-layer control channels, for which the information blocks are small compared to data transmission and hybrid-ARQ is not used, polar codes have been selected. For the smallest control payloads, Reed!Muller codes are used.

## Initial Access
Initial access is the procedures allowing a device to find a cell to camp on, receive the necessary system information, and to request a connection through random access.
- There is a pair of downlink signals, the primary synchronization signal (PSS) and the secondary synchronization signal (SSS), that is used by devices to find, synchronize to, and identify a network;
- There is a downlink physical broadcast channel (PBCH) transmitted together with the PSS/SSS. The PBCH carries a minimum amount of system information including an indication where the remaining broadcast system information is transmitted. In the context of NR, the PSS, SSS, and PBCH are jointly referred to as a synchronization signal (SS) block;
- There is a four-stage random-access procedure, commencing with the uplink transmission of a random-access preamble.
However, there are some important differences between LTE and NR in terms of initial access. These differences come mainly from the ultra-lean principle and the beam-centric design.
## INTERWORKING AND LTE COEXISTENCE
Two coexistence scenarios were identified in 3GPP and guided the NR design:
- In the first scenario, illustrated in the left part of Fig. 5.6, there is LTE/NR coexistence in both downlink and uplink. Note that this is relevant for both paired and unpaired spectra although a paired spectrum is used in the illustration.
- In the second scenario, illustrated in the right part of Fig. 5.6, there is coexistence only in the uplink transmission direction, typically within the uplink part of a lower-frequency paired spectrum, with NR downlink transmission taking place in the spectrum dedicated to NR, typically at higher frequencies. This scenario attempts to address the uplink!downlink imbalance discussed above. NR supports a supplementary uplink (SUL) to specifically handle this scenario.
![image](https://github.com/user-attachments/assets/fd2ca330-5368-4c5f-9ed3-2ae5d2d49b70)
