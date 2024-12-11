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
