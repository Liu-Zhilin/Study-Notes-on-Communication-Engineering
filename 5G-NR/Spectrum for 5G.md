# Spectrum for 5G
**1G,2G**:  800-900 MHz

**3G**: 2GHz -> **3G,4G**: 450MHz - 6GHz

**5g**:3.3GHz-4.2GHz、 4.4GHz-5.0GHz和毫米波频段26GHz/28GHz/39GHz。

- Bands at **lower frequencies** are good for **wide-area coverage** deployments.

- Bands at **HIGHER frequencies** are good for new usage scenarios requiring high data rates and is also suitable for massive
MIMO implementation, where arrays with many elements can be implemented with reasonable size.
![image](https://github.com/user-attachments/assets/2af5815f-b334-43fd-8bff-3f037974051d)
- 低频：2GHz以下的频段，由于传输损耗低，适用于覆盖，即提高广域和深度的覆盖，包括室内覆盖（室内似乎更倾向于中频或高频）。
  最感兴趣的是600MHz和700MHz，对应的5G频段是n71和n28。
  maximum of 20 MHz channel bandwidth is expected
- 中频：3GHz~6GHz的频段,通过更宽的信道带宽提供覆盖、容量和高速率。最感兴趣的是3300MHz~4200MHz，
  中国主要对3300MHz~3600MHz感兴趣，还有些频段如4800MHz~5000MHz也感兴趣。
  Channel bandwidths up to 100 MHz are possible.通过载波聚合可以达到更大的带宽。
  
  实现载波聚合的方式主要有两种：
  - 一种是在同一频段内聚合信道，这被称为带内载波聚合；
  - 另一种是在不同频段聚合信道，称为带间载波聚合。
    
  载波聚合的实质是将两个或更多的独立连接，在物理上虽然分离，但在逻辑上将它们合并为一个单一的、更大的、更快的连接。
- 高频：24GHz以上的频段，即毫米波频段，适用于超高容量的本地热点覆盖。最感兴趣的是24.25GHz~29.5GHz，对应的5G频段是n257和n258。
  Channel bandwidths up to 400 MHz are defined for these bands.通过载波聚合可以达到更大的带宽。
