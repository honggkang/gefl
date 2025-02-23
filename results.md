---
title: Results
layout: home
nav_order: 3
---


Mean classification acc. (%) evaluation of different methods on the MNIST, FMNIST, and CIFAR10 dataset.

<table>
   <tr>
       <th></th>
       <th>MNIST</th>
       <th>FMNIST</th>
       <th>CIFAR10</th>
   </tr>
   <tr>
       <td>FedAvg</td>
       <td>92.62</td>
       <td>80.58</td>
       <td>55.65</td>
   </tr>
   <tr>
       <td>FedProx</td>
       <td>92.57</td>
       <td>80.50</td>
       <td>55.10</td>
   </tr>
   <tr>
       <td>AvgKD</td>
       <td>92.81</td>
       <td>77.12</td>
       <td>26.36</td>
   </tr>
   <tr>
       <td>FedDF</td>
       <td>91.39</td>
       <td>58.81</td>
       <td>57.17</td>
   </tr>
   <tr>
       <td>LG-FedAvg</td>
       <td>92.71</td>
       <td>80.61</td>
       <td>54.49</td>
   </tr>
   <tr>
       <td><b>GeFL</b> (FedDCGAN)</td>
       <td>95.32</td>
       <td><b>83.11</b></td>
       <td>58.45</td>
   </tr>
   <tr>
       <td><b>GeFL</b> (FedCVAE)</td>
       <td>94.46</td>
       <td>82.33</td>
       <td>55.80</td>
   </tr>
   <tr>
       <td><b>GeFL</b> (FedDDPM<sub>w=0</sub>)</td>
       <td><b>96.44</b></td>
       <td>82.43</td>
       <td>59.36</td>
   </tr>
   <tr>
       <td><b>GeFL</b> (FedDDPM<sub>w=2</sub>)</td>
       <td>95.17</td>
       <td>81.51</td>
       <td><b>58.47</b></td>
   </tr>
</table>

Mean classification acc. (%) comparison to data augmentation. GeFL outperforms other baselines and is effective combined with data augmentation.
<table>
   <tr>
       <th></th>
       <th>FedAvg</th>
       <th>GeFL (FedDCGAN)</th>
   </tr>
   <tr>
       <td>None</td>
       <td>55.65<sub>&plusmn;0.68</sub></td>
       <td>58.45<sub>&plusmn;0.49</sub></td>
   </tr>
   <tr>
       <td>MixUp</td>
       <td>60.07<sub>&plusmn;1.13</sub></td>
       <td><b>62.67<sub>&plusmn;0.24</sub></b></td>
   </tr>
   <tr>
       <td>CutMix</td>
       <td>58.95<sub>&plusmn;0.61</sub></td>
       <td>61.66<sub>&plusmn;0.41</sub></td>
   </tr>
   <tr>
       <td>AugMix</td>
       <td>53.96<sub>&plusmn;0.37</sub></td>
       <td>56.47<sub>&plusmn;0.25</sub></td>
   </tr>
   <tr>
       <td>AutoAugment</td>
       <td>56.99<sub>&plusmn;0.43</sub></td>
       <td>59.97<sub>&plusmn;0.38</sub></td>
   </tr>
</table>



Scalability in client numbers of GeFL and GeFL-F on MNIST, FMNIST, SVHN, and CIFAR dataset. GeFL-F exhibits less performance degradation in a large number of clients compared to GeFL.

<figure>
    <img src='./resources/geflf_mnist.png' alt="drawing" width="400"/>
    <figcaption>MNIST</figcaption>
    <img src='./resources/geflf_fmnist.png' alt="drawing" width="400"/>
    <figcaption>FMNIST</figcaption>
</figure>

<figure>
    <img src='./resources/geflf_svhn.png' alt="drawing" width="400"/>
    <figcaption>SVHN</figcaption>
    <img src='./resources/geflf_cifar.png' alt="drawing" width="400"/>
    <figcaption>CIFAR10</figcaption>
</figure>

<!-- ![MNIST](./resources/geflf_mnist.png)*MNIST*
![FMNIST](./resources/geflf_fmnist.png)*FMNIST*

![SVHN](./resources/geflf_svhn.png)*SVHN*
![CIFAR10](./resources/geflf_cifar.png)*CIFAR10* -->

<!-- <img src="./resources/geflf_fmnist.png" alt="drawing" width="400"/>
<img src="./resources/geflf_svhn.png" alt="drawing" width="400"/>
<img src="./resources/geflf_cifar.png" alt="drawing" width="400"/> -->

Comparison of privacy, communication and computational costs in GeFL and GeFL-F. Lower values indicate better conditions for each component.

<img src="./resources/privacy_scalability.png" alt="drawing" width="800"/>