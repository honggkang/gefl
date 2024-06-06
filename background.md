---
title: Background
layout: home
nav_order: 2
---


## Federated Learning 
Federated learning (FL) is a machine learning setting where multiple entities (clients) collaborate in solving a machine learning problem, under the coordination of a central server or service provider. Each client’s raw data is stored locally and not exchanged or transferred; instead, focused updates intended for immediate aggregation are used to achieve the learning objective. [1]

- Establishing a model exploiting a vast amount of data preserving the privacy
    - Data is stored at local users
    - Local users transmit model parameters instead of raw data
- Applications [2]
    - (Cross-device FL) Smart phones: next-word prediction [3], face detection, and voice recognition [4]
    - (Cross-silo FL) Hospitals: strict privacy practices [5]

## Edge Devices
- Growing amount of edge devices
- A vast amount of data from edge devices
- *Federated learning for on-device AI*

<img src="./resources/cont_learning.png" width="420"/>
<img src="./resources/iot_devices.png" width="260"/>

## System Heterogeneity
- Computing power
    - Hardware
        - CPU / GPU / NPU / FPGA / ASIC 
    - Run-time dynamics
- Communications
    - 3G/4G/5G/Wi-Fi
- Memory, battery, cloud-aided / on-device AI …

<img src="./resources/hw_het.png" width="300"/>
<img src="./resources/flop_mem_het.png" width="350"/>
<img src="./resources/comm_het.png" width="350"/>

## Challenges of FL in this Era
- Increasing model size + more heterogeneous devices
- **FL must tolerate heterogeneous systems**

<img src="./resources/inc_model.png" alt="drawing" width="400"/>
<img src="./resources/tolerantFL.png" alt="drawing" width="150"/>


---
[1] Peter Kairouz et al., Advances and Open Problems in Federated Learning, 2021.

[2] T. Li, A. K. Sahu, A. Talwalkar and V. Smith, "Federated Learning: Challenges, Methods, and Future Directions," IEEE Signal Processing Magazine, vol. 37, no. 3, pp. 50-60, May 2020.

[3] https://support.google.com/gboard/answer/12373137?hl=en & Hard, Andrew, et al. "Federated learning for mobile keyboard prediction." arXiv preprint arXiv:1811.03604 (2018).

[4] https://support.google.com/assistant/answer/10176224?hl=en

[5] Dou, Q., So, T.Y., Jiang, M. et al. Federated deep learning for detecting COVID-19 lung abnormalities in CT: a privacy-preserving multinational validation study. npj Digit. Med. 4, 60 (2021).

