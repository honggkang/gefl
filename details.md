---
title: Details
layout: home
nav_order: 4
---


# Experimental Details on GeFL

## Table II
### CIFAR10
<table>
    <caption>FL parameters</caption>
    <tbody>
        <tr>
            <td>Num of users |<i>C</i>|</td>
            <td>10</td>
        </tr>
        <tr>
            <td>Num of heterogeneous models <i>M</i></td>
            <td>10</td>
        </tr>
        <tr>
            <td>Data fraction</td>
            <td>0.5</td>
        </tr>
    </tbody>
</table>

<br>

<table>
    <caption>Generative mdoel (GM) parameters</caption>
    <thead>
        <tr>
            <th></th>
            <th>DCGAN</th>
            <th>CVAE</th>
            <th>DDPM w=0</th>
            <th>DDPM w=2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Optimizer</td>
            <td>Adam</td>
            <td>Adam</td>
            <td>Adam</td>
            <td>Adam</td>
        </tr>
        <tr>
            <td>Learning rate <i>β</i></td>
            <td>2e-4</td>
            <td>1e-3</td>
            <td>1e-4</td>
            <td>1e-4</td>
        </tr>
        <tr>
            <td>Weight decay</td>
            <td>None</td>
            <td>1e-3</td>
            <td>None</td>
            <td>None</td>
        </tr>
        <tr>
            <td>b1, b2 (Adam)</td>
            <td>0.5, 0.999</td>
            <td>None</td>
            <td>None</td>
            <td>None</td>
        </tr>
        <tr>
            <td>Batch size <i>B</i></td>
            <td>128</td>
            <td>128</td>
            <td>128</td>
            <td>128</td>
        </tr>        
        <tr>
            <td>Communication rounds for training generative model<i>T<sub>KA</sub></i></td>
            <td>200 (100/100)</td>
            <td>200</td>
            <td>200</td>
            <td>200</td>
        </tr>
        <tr>
            <td>Local epochs for training generative model<i>T<sub>g</sub></i></td>
            <td>5</td>
            <td>5</td>
            <td>5</td>
            <td>5</td>
        </tr>
        <tr>
            <td>Image size</td>
            <td>3 x 32 x 32</td>
            <td>3 x 32 x 32</td>
            <td>3 x 32 x 32</td>
            <td>3 x 32 x 32</td>
        </tr>
        <tr>
            <td>Latent dim (<i>d<sub>g</sub>, d<sub>d</sub></i>)</td>
            <td>256/64 (for G/D)</td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>Latent size</td>
            <td></td>
            <td>50</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>n_feat (of Unet in DDPM)</td>
            <td></td>
            <td></td>
            <td>128</td>
            <td>128</td>
        </tr>
        <tr>
            <td>Time step</td>
            <td></td>
            <td></td>
            <td>400</td>
            <td>400</td>
        </tr>
    </tbody>
</table>
* DCGAN was trained for 100 rounds and additionally updated for 100 rounds during the training of target networks.

<br>

<table>
    <caption>Target network (CNN) parameters</caption>
    <thead>
        <tr>
            <th></th>
            <th>Target networks</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Optimizer</td>
            <td>SGD</td>
        </tr>
        <tr>
            <td>Learning rate <i>α</i></td>
            <td>0.1</td>
        </tr>
        <tr>
            <td>Communication rounds for training target network<i>T<sub>TN</sub></i></td>
            <td>100</td>
        </tr>
        <tr>
            <td>Local epochs for training training target network by real samples <i>T<sub>r</sub></i></td>
            <td>5</td>
        </tr>
        <tr>
            <td>Local epochs for training training target network by synthetic samples <i>T<sub>s</sub></i></td>
            <td>1</td>
        </tr>
        <tr>
            <td>Batch size <i>B</i></td>
            <td>128</td>
        </tr>
    </tbody>
</table>
Baselines

- FedProx: 1e-2 multiplied to proximal term
- AvgKD: pseudo labels are aggregated from the outputs of 10 heterogeneous models. 
- FedDF: CIFAR100 as public dataset
- LG-FedAvg: the first conv layer was employed as averaging over all the heterogeneous models while the other layers are averaged across submodels. 

### MNIST/FMNIST
<table>
    <caption>FL parameters</caption>
    <tbody>
        <tr>
            <td>Num of users |<i>C</i>|</td>
            <td>10</td>
        </tr>
        <tr>
            <td>Num of heterogeneous models <i>M</i></td>
            <td>10</td>
        </tr>
        <tr>
            <td>Data fraction</td>
            <td>0.1</td>
        </tr>
    </tbody>
</table>

<br>

<table>
    <caption>Generative mdoel (GM) parameters</caption>
    <thead>
        <tr>
            <th></th>
            <th>DCGAN</th>
            <th>CVAE</th>
            <th>DDPM w=0</th>
            <th>DDPM w=2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Optimizer</td>
            <td>Adam</td>
            <td>Adam</td>
            <td>Adam</td>
            <td>Adam</td>
        </tr>
        <tr>
            <td>Learning rate <i>β</i></td>
            <td>2e-4</td>
            <td>1e-3</td>
            <td>1e-4</td>
            <td>1e-4</td>
        </tr>
        <tr>
            <td>Weight decay</td>
            <td>None</td>
            <td>1e-3</td>
            <td>None</td>
            <td>None</td>
        </tr>
        <tr>
            <td>b1, b2 (Adam)</td>
            <td>0.5, 0.999</td>
            <td>None</td>
            <td>None</td>
            <td>None</td>
        </tr>
        <tr>
            <td>Batch size <i>B</i></td>
            <td>64</td>
            <td>64</td>
            <td>64</td>
            <td>64</td>
        </tr>        
        <tr>
            <td>Communication rounds for training generative model<i>T<sub>KA</sub></i></td>
            <td>100 (50/50)</td>
            <td>100</td>
            <td>100</td>
            <td>100</td>
        </tr>
        <tr>
            <td>Local epochs for training generative model<i>T<sub>g</sub></i></td>
            <td>5</td>
            <td>5</td>
            <td>5</td>
            <td>5</td>
        </tr>
        <tr>
            <td>Image size</td>
            <td>1 x 32 x 32</td>
            <td>1 x 32 x 32</td>
            <td>1 x 32 x 32</td>
            <td>1 x 32 x 32</td>
        </tr>
        <tr>
            <td>Latent dim (<i>d<sub>g</sub>, d<sub>d</sub></i>)</td>
            <td>128/128 (for G/D)</td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>Latent size</td>
            <td></td>
            <td>16</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>n_feat (of Unet in DDPM)</td>
            <td></td>
            <td></td>
            <td>128</td>
            <td>128</td>
        </tr>
        <tr>
            <td>Time step</td>
            <td></td>
            <td></td>
            <td>100</td>
            <td>100</td>
        </tr>
    </tbody>
</table>
* DCGAN was trained for 50 rounds and additionally updated for 50 rounds during the training of target networks.

<br>

<table>
    <caption>Target network (CNN) parameters</caption>
    <thead>
        <tr>
            <th></th>
            <th>Target networks</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Optimizer</td>
            <td>SGD</td>
        </tr>
        <tr>
            <td>Learning rate <i>α</i></td>
            <td>0.1</td>
        </tr>
        <tr>
            <td>Communication rounds for training target network<i>T<sub>TN</sub></i></td>
            <td>100</td>
        </tr>
        <tr>
            <td>Local epochs for training training target network by real samples <i>T<sub>r</sub></i></td>
            <td>5</td>
        </tr>
        <tr>
            <td>Local epochs for training target network by synthetic samples <i>T<sub>s</sub></i></td>
            <td>1</td>
        </tr>
        <tr>
            <td>Batch size <i>B</i></td>
            <td>64</td>
        </tr>
    </tbody>
</table>
Baselines

- FedProx: 1e-2 multiplied to proximal term
- AvgKD: Pseudo labels are aggregated from the outputs of 10 heterogeneous models.
- FedDF: SVHN as public dataset for MNIST & CIFAR10 as public dataset for FMNIST
- LG-FedAvg: the first conv layer was employed as averaging over all the heterogeneous models while the other layers are averaged across submodels. 

## Table III

<table>
      <thead>
          <tr>
              <th>FID/IS parameter</th>
              <th></th>
          </tr>
      </thead>
      <tbody>
          <tr>
              <td># of samples used</td>
              <td>1000</td>
          </tr>
      </tbody>
</table>

<table>
    <thead>
        <tr>
            <th>MND parameter</th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td># of validation samples</td>
            <td>600</td>
        </tr>
        <tr>
            <td># of synthetic samples</td>
            <td>600</td>
        </tr>
        <tr>
            <td># of training samples (for averaging)</td>
            <td>1000</td>
        </tr>
        <tr>
            <td>Distance measure</td>
            <td>LPIPS</td>
        </tr>
    </tbody>
</table>

## Table IV
- Generative model: DCGAN
- All the parameters settings are identical to Table 1

Note: DA techniques are used only during target network training (not in training generative models) 


## Figure 4
### CIFAR10
<table>
    <caption>FL parameters</caption>
    <tbody>
        <tr>
            <td>Num of users |<i>C</i>|</td>
            <td>10</td>
        </tr>
        <tr>
            <td>Num of heterogeneous models <i>M</i></td>
            <td>10</td>
        </tr>
        <tr>
            <td>Data fraction</td>
            <td>0.5</td>
        </tr>
    </tbody>
</table>

<br>

<table>
    <caption>Feature-generative mdoel (GM) parameters</caption>
    <thead>
        <tr>
            <th></th>
            <th>DCGAN</th>
            <th>CVAE</th>
            <th>DDPM w=0</th>
            <th>DDPM w=2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Optimizer</td>
            <td>Adam</td>
            <td>Adam</td>
            <td>Adam</td>
            <td>Adam</td>
        </tr>
        <tr>
            <td>Learning rate <i>β</i></td>
            <td>2e-4</td>
            <td>1e-3</td>
            <td>1e-4</td>
            <td>1e-4</td>
        </tr>
        <tr>
            <td>Weight decay</td>
            <td>None</td>
            <td>1e-3</td>
            <td>None</td>
            <td>None</td>
        </tr>
        <tr>
            <td>b1, b2 (Adam)</td>
            <td>0.5, 0.999</td>
            <td>None</td>
            <td>None</td>
            <td>None</td>
        </tr>
        <tr>
            <td>Batch size <i>B</i></td>
            <td>128</td>
            <td>128</td>
            <td>128</td>
            <td>128</td>
        </tr>        
        <tr>
            <td>Communication rounds for training generative model<i>T<sub>KA</sub></i></td>
            <td>200 (100/100)</td>
            <td>200</td>
            <td>200</td>
            <td>200</td>
        </tr>
        <tr>
            <td>Local epochs for training generative model<i>T<sub>g</sub></i></td>
            <td>5</td>
            <td>5</td>
            <td>5</td>
            <td>5</td>
        </tr>
        <tr>
            <td>Image size</td>
            <td>10 x 16 x 16</td>
            <td>10 x 16 x 16</td>
            <td>10 x 16 x 16</td>
            <td>10 x 16 x 16</td>
        </tr>
        <tr>
            <td>Latent dim (<i>d<sub>g</sub>, d<sub>d</sub></i>)</td>
            <td>256/64 (for G/D)</td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>Latent size</td>
            <td></td>
            <td>50</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>n_feat (of Unet in DDPM)</td>
            <td></td>
            <td></td>
            <td>128</td>
            <td>128</td>
        </tr>
        <tr>
            <td>Time step</td>
            <td></td>
            <td></td>
            <td>500</td>
            <td>500</td>
        </tr>
    </tbody>
</table>
* DCGAN was trained for 100 rounds and additionally updated for 100 rounds during the training of target networks.

<br>

<table>
    <caption>Target network (CNN) parameters</caption>
    <thead>
        <tr>
            <th></th>
            <th>Target networks</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Optimizer</td>
            <td>SGD</td>
        </tr>
        <tr>
            <td>Learning rate <i>α</i></td>
            <td>0.1</td>
        </tr>
        <tr>
            <td>Communication rounds for warming up feature extractor<i>T<sub>FE</sub></i></td>
            <td>50</td>
        </tr>
        <tr>
            <td>Local epochs for training feature extractor <i>T<sub>w</sub></i></td>
            <td>5</td>
        </tr>
        <tr>
            <td>Communication rounds for training target network<i>T<sub>TN</sub></i></td>
            <td>100</td>
        </tr>
        <tr>
            <td>Local epochs for training target network by real samples <i>T<sub>r</sub></i></td>
            <td>5</td>
        </tr>
        <tr>
            <td>Local epochs for training target network by synthetic samples <i>T<sub>s</sub></i></td>
            <td>1</td>
        </tr>
        <tr>
            <td>Batch size <i>B</i></td>
            <td>128</td>
        </tr>
    </tbody>
</table>

### MNIST/FMNIST/SVHN
<table>
    <caption>FL parameters</caption>
    <tbody>
        <tr>
            <td>Num of users |<i>C</i>|</td>
            <td>10</td>
        </tr>
        <tr>
            <td>Num of heterogeneous models <i>M</i></td>
            <td>10</td>
        </tr>
        <tr>
            <td>Data fraction</td>
            <td>0.1</td>
        </tr>
    </tbody>
</table>

<br>

<table>
    <caption>Feature-generative mdoel (GM) parameters</caption>
    <thead>
        <tr>
            <th></th>
            <th>DCGAN</th>
            <th>CVAE</th>
            <th>DDPM w=0</th>
            <th>DDPM w=2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Optimizer</td>
            <td>Adam</td>
            <td>Adam</td>
            <td>Adam</td>
            <td>Adam</td>
        </tr>
        <tr>
            <td>Learning rate <i>β</i></td>
            <td>2e-4</td>
            <td>1e-3</td>
            <td>1e-4</td>
            <td>1e-4</td>
        </tr>
        <tr>
            <td>Weight decay</td>
            <td>None</td>
            <td>1e-3</td>
            <td>None</td>
            <td>None</td>
        </tr>
        <tr>
            <td>b1, b2 (Adam)</td>
            <td>0.5, 0.999</td>
            <td>None</td>
            <td>None</td>
            <td>None</td>
        </tr>
        <tr>
            <td>Batch size <i>B</i></td>
            <td>64</td>
            <td>64</td>
            <td>64</td>
            <td>64</td>
        </tr>        
        <tr>
            <td>Communication rounds for training generative model<i>T<sub>KA</sub></i></td>
            <td>100 (50/50)</td>
            <td>100</td>
            <td>100</td>
            <td>100</td>
        </tr>
        <tr>
            <td>Local epochs for training generative model<i>T<sub>g</sub></i></td>
            <td>5</td>
            <td>5</td>
            <td>5</td>
            <td>5</td>
        </tr>
        <tr>
            <td>Image size</td>
            <td>3 x 16 x 16</td>
            <td>3 x 16 x 16</td>
            <td>3 x 16 x 16</td>
            <td>3 x 16 x 16</td>
        </tr>
        <tr>
            <td>Latent dim (<i>d<sub>g</sub>, d<sub>d</sub></i>)</td>
            <td>128/128 (for G/D)</td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>Latent size</td>
            <td></td>
            <td>16</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>n_feat (of Unet in DDPM)</td>
            <td></td>
            <td></td>
            <td>128</td>
            <td>128</td>
        </tr>
        <tr>
            <td>Time step</td>
            <td></td>
            <td></td>
            <td>100</td>
            <td>100</td>
        </tr>
    </tbody>
</table>
* DCGAN was trained for 50 rounds and additionally updated for 50 rounds during the training of target networks.

<br>

<table>
    <caption>Target network (CNN) parameters (MNIST/FMNIST)</caption>
    <thead>
        <tr>
            <th></th>
            <th>Target networks</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Optimizer</td>
            <td>SGD</td>
        </tr>
        <tr>
            <td>Learning rate <i>α</i></td>
            <td>0.1</td>
        </tr>
        <tr>
            <td>Communication rounds for warming up feature extractor<i>T<sub>FE</sub></i></td>
            <td>20</td>
        </tr>
        <tr>
            <td>Local epochs for training feature extractor <i>T<sub>w</sub></i></td>
            <td>5</td>
        </tr>
        <tr>
            <td>Communication rounds for training target network<i>T<sub>TN</sub></i></td>
            <td>50</td>
        </tr>
        <tr>
            <td>Local epochs for training target network by real samples <i>T<sub>r</sub></i></td>
            <td>5</td>
        </tr>
        <tr>
            <td>Local epochs for training target network by synthetic samples <i>T<sub>s</sub></i></td>
            <td>1</td>
        </tr>
        <tr>
            <td>Batch size <i>B</i></td>
            <td>64</td>
        </tr>
    </tbody>
</table>

### SVHN

<table>
    <caption>Target network (CNN) parameters (SVHN)</caption>
    <thead>
        <tr>
            <th></th>
            <th>Target networks</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Optimizer</td>
            <td>SGD</td>
        </tr>
        <tr>
            <td>Learning rate <i>α</i></td>
            <td>0.1</td>
        </tr>
        <tr>
            <td>Communication rounds for warming up feature extractor<i>T<sub>FE</sub></i></td>
            <td>50</td>
        </tr>
        <tr>
            <td>Local epochs for training feature extractor <i>T<sub>w</sub></i></td>
            <td>5</td>
        </tr>
        <tr>
            <td>Communication rounds for training target network<i>T<sub>TN</sub></i></td>
            <td>100</td>
        </tr>
        <tr>
            <td>Local epochs for training target network by real samples <i>T<sub>r</sub></i></td>
            <td>5</td>
        </tr>
        <tr>
            <td>Local epochs for training target network by synthetic samples <i>T<sub>s</sub></i></td>
            <td>1</td>
        </tr>
        <tr>
            <td>Batch size <i>B</i></td>
            <td>64</td>
        </tr>
    </tbody>
</table>

## Table VII
- Generative model: DCGAN
- All the parameters settings are identical to Table 1

## Figure 7
  <table>
      <thead>
          <tr>
              <th>Total dimension</th>
              <th>Feat size</th>
              <th>HL</th>
              <th>Comm round of training common FE</th>
              <th>Comm round of training header</th>
          </tr>
      </thead>
      <tbody>
          <tr>
              <td>1024</td>
              <td>1*32*32</td>
              <td>0</td>
              <td>0</td>
              <td>70</td>
          </tr>
          <tr>
              <td>768</td>
              <td>3*16*16</td>
              <td>1</td>
              <td>20</td>
              <td>50</td>
          </tr>
          <tr>
              <td>640</td>
              <td>10*8*8</td>
              <td>2</td>
              <td>20</td>
              <td>50</td>
          </tr>
          <tr>
              <td>320</td>
              <td>20*4*4</td>
              <td>3</td>
              <td>20</td>
              <td>50</td>
          </tr>
          <tr>
              <td>160</td>
              <td>40*2*2</td>
              <td>4</td>
              <td>50</td>
              <td>20</td>
          </tr>
          <tr>
              <td>80</td>
              <td>80*1*1</td>
              <td>5</td>
              <td>60</td>
              <td>10</td>
          </tr>
          <tr>
              <td>0</td>
              <td>0</td>
              <td>6</td>
              <td>70</td>
              <td>0</td>
          </tr>
      </tbody>
  </table>

  - Homogeneity level (HL) 0 denotes the heterogeneous models without common feature extractor (FE) that only headers of models need to be trained.
  - HL 6 denotes the homogeneous models where all the models consists of only common FE (i.e., common FE is the whole model).

## Figure 8

  - Models are described as in details on Figure 7.
  - MND was evaluated as in Table 2.

## Figure 10

  - Real data scale : 0.01, 0.05, 0.1, 0.5, 1
  - GeFL w/ Syn 5: Local epochs for training training target network by synthetic samples <i>T<sub>s</sub></i>=5
  - GeFL w/ Syn 1: Local epochs for training training target network by synthetic samples <i>T<sub>s</sub></i>=1
  - Other parameters are identical to Table 1 

## Table 8

- Same as Table 7 

## Model architecture
In following tables, conv(c,k,p) denotes a 2d convolutional layer, where c is the output channel size, k is the kernel size, and p is the padding size. bn(c) represents a batch normalization layer with c denoting the channel size. The term relu denotes the rectified linear layer, and maxpool(k,s,p) denotes a max-pooling layer. where k is the kernel size, s is the stride, and p is the padding size. Finally, fc(in/out) indicates a fully connected layer, where in is the number of input nodes and out is the number of output nodes.

### MNIST
<table>
  <thead>
    <tr>
      <th>CNN-1</th>
      <th>CNN-2</th>
      <th>CNN-3</th>
      <th>CNN-4</th>
      <th>CNN-5</th>
      <th>CNN-6</th>
      <th>CNN-7</th>
      <th>CNN-8</th>
      <th>CNN-9</th>
      <th>CNN-10</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
    </tr>
    <tr>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
    </tr>
    <tr>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
    </tr>
    <tr>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
    </tr>
    <tr>
      <td>conv(16,3×3,1)</td>
      <td>conv(16,3×3,1)</td>
      <td>conv(20,3×3,1)</td>
      <td>conv(10,3×3,1)</td>
      <td>conv(16,3×3,1)</td>
      <td>conv(20,3×3,1)</td>
      <td>conv(10,3×3,1)</td>
      <td>conv(16,3×3,1)</td>
      <td>conv(20,3×3,1)</td>
      <td>conv(10,3×3,1)</td>
    </tr>
    <tr>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
    </tr>
    <tr>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
    </tr>
    <tr>
      <td></td>
      <td>conv(32,3×3,1)</td>
      <td>conv(40,3×3,1)</td>
      <td>conv(20,3×3,1)</td>
      <td>conv(32,3×3,1)</td>
      <td>conv(40,3×3,1)</td>
      <td>conv(20,3×3,1)</td>
      <td>conv(32,3×3,1)</td>
      <td>conv(40,3×3,1)</td>
      <td>conv(20,3×3,1)</td>
    </tr>
    <tr>
      <td></td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
    </tr>
    <tr>
      <td></td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>conv(64,3×3,1)</td>
      <td>conv(80,3×3,1)</td>
      <td>conv(40,3×3,1)</td>
      <td>conv(64,3×3,1)</td>
      <td>conv(80,3×3,1)</td>
      <td>conv(40,3×3,1)</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>conv(64,3×3,1)</td>
      <td>conv(80,3×3,1)</td>
      <td>conv(40,3×3,1)</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
    </tr>
  </tbody>
</table>


### FMNIST
<table>
  <thead>
    <tr>
      <th>CNN-1</th>
      <th>CNN-2</th>
      <th>CNN-3</th>
      <th>CNN-4</th>
      <th>CNN-5</th>
      <th>CNN-6</th>
      <th>CNN-7</th>
      <th>CNN-8</th>
      <th>CNN-9</th>
      <th>CNN-10</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
    </tr>
    <tr>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
    </tr>
    <tr>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
    </tr>
    <tr>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
    </tr>
    <tr>
      <td>conv(16,3×3,1)</td>
      <td>conv(16,3×3,1)</td>
      <td>conv(20,3×3,1)</td>
      <td>conv(10,3×3,1)</td>
      <td>conv(16,3×3,1)</td>
      <td>conv(20,3×3,1)</td>
      <td>conv(10,3×3,1)</td>
      <td>conv(16,3×3,1)</td>
      <td>conv(20,3×3,1)</td>
      <td>conv(10,3×3,1)</td>
    </tr>
    <tr>
      <td>bn(16)</td>
      <td>bn(16)</td>
      <td>bn(20)</td>
      <td>bn(10)</td>
      <td>bn(16)</td>
      <td>bn(20)</td>
      <td>bn(10)</td>
      <td>bn(16)</td>
      <td>bn(20)</td>
      <td>bn(10)</td>
    </tr>
    <tr>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
    </tr>
    <tr>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
    </tr>
    <tr>
      <td></td>
      <td>conv(32,3×3,1)</td>
      <td>conv(40,3×3,1)</td>
      <td>conv(20,3×3,1)</td>
      <td>conv(32,3×3,1)</td>
      <td>conv(40,3×3,1)</td>
      <td>conv(20,3×3,1)</td>
      <td>conv(32,3×3,1)</td>
      <td>conv(40,3×3,1)</td>
      <td>conv(20,3×3,1)</td>
    </tr>
    <tr>
      <td></td>
      <td>bn(32)</td>
      <td>bn(40)</td>
      <td>bn(20)</td>
      <td>bn(32)</td>
      <td>bn(40)</td>
      <td>bn(20)</td>
      <td>bn(32)</td>
      <td>bn(40)</td>
      <td>bn(20)</td>
    </tr>
    <tr>
      <td></td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
    </tr>
    <tr>
      <td></td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>conv(64,3×3,1)</td>
      <td>conv(80,3×3,1)</td>
      <td>conv(40,3×3,1)</td>
      <td>conv(64,3×3,1)</td>
      <td>conv(80,3×3,1)</td>
      <td>conv(40,3×3,1)</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>bn(64)</td>
      <td>bn(80)</td>
      <td>bn(40)</td>
      <td>bn(64)</td>
      <td>bn(80)</td>
      <td>bn(40)</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>conv(128,3×3,1)</td>
      <td>conv(100,3×3,1)</td>
      <td>conv(80,3×3,1)</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>bn(128)</td>
      <td>bn(100)</td>
      <td>bn(80)</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
    </tr>
    <tr>
      <td>fc(1024/10)</td>
      <td>fc(512/10)</td>
      <td>fc(640/10)</td>
      <td>fc(320/10)</td>
      <td>fc(256/10)</td>
      <td>fc(320/10)</td>
      <td>fc(160/10)</td>
      <td>fc(128/10)</td>
      <td>fc(100/10)</td>
      <td>fc(80/10)</td>
    </tr>
  </tbody>
</table>

### CIFAR10
<table>
  <thead>
    <tr>
      <th>CNN-1</th>
      <th>CNN-2</th>
      <th>CNN-3</th>
      <th>CNN-4</th>
      <th>CNN-5</th>
      <th>CNN-6</th>
      <th>CNN-7</th>
      <th>CNN-8</th>
      <th>CNN-9</th>
      <th>CNN-10</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
      <td>conv(3,3×3,1)</td>
    </tr>
    <tr>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
      <td>bn(3)</td>
    </tr>
    <tr>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
    </tr>
    <tr>
      <td>conv(10,3×3,1)</td>
      <td>conv(10,3×3,1)</td>
      <td>conv(10,3×3,1)</td>
      <td>conv(10,3×3,1)</td>
      <td>conv(10,3×3,1)</td>
      <td>conv(10,3×3,1)</td>
      <td>conv(10,3×3,1)</td>
      <td>conv(10,3×3,1)</td>
      <td>conv(10,3×3,1)</td>
      <td>conv(10,3×3,1)</td>
    </tr>
    <tr>
      <td>bn(10)</td>
      <td>bn(10)</td>
      <td>bn(10)</td>
      <td>bn(10)</td>
      <td>bn(10)</td>
      <td>bn(10)</td>
      <td>bn(10)</td>
      <td>bn(10)</td>
      <td>bn(10)</td>
      <td>bn(10)</td>
    </tr>
    <tr>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
    </tr>
    <tr>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
    </tr>
    <tr>
      <td>conv(16,3×3,1)</td>
      <td>conv(16,3×3,1)</td>
      <td>conv(20,3×3,1)</td>
      <td>conv(10,3×3,1)</td>
      <td>conv(10,3×3,1)</td>
      <td>conv(20,3×3,1)</td>
      <td>conv(10,3×3,1)</td>
      <td>conv(16,3×3,1)</td>
      <td>conv(20,3×3,1)</td>
      <td>conv(10,3×3,1)</td>
    </tr>
    <tr>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
    </tr>
    <tr>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
    </tr>
    <tr>
      <td></td>
      <td>conv(32×3,1)</td>
      <td>conv(40,3×3,1)</td>
      <td>conv(20,3×3,1)</td>
      <td>conv(32,3×3,1)</td>
      <td>conv(40,3×3,1)</td>
      <td>conv(20,3×3,1)</td>
      <td>conv(32,3×3,1)</td>
      <td>conv(40,3×3,1)</td>
      <td>conv(20,3×3,1)</td>
    </tr>
    <tr>
      <td></td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
    </tr>
    <tr>
      <td></td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>conv(64,3×3,1)</td>
      <td>conv(80,3×3,1)</td>
      <td>conv(40,3×3,1)</td>
      <td>conv(64,3×3,1)</td>
      <td>conv(80,3×3,1)</td>
      <td>conv(40,3×3,1)</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>conv(128,3×3,1)</td>
      <td>conv(100,3×3,1)</td>
      <td>conv(80,3×3,1)</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>relu</td>
      <td>relu</td>
      <td>relu</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
      <td>maxpool(2×2,2,0)</td>
    </tr>
    <tr>
      <td>fc(1024/10)</td>
      <td>fc(512/10)</td>
      <td>fc(640/10)</td>
      <td>fc(320/10)</td>
      <td>fc(256/10)</td>
      <td>fc(320/10)</td>
      <td>fc(160/10)</td>
      <td>fc(128/10)</td>
      <td>fc(100/10)</td>
      <td>fc(80/10)</td>
    </tr>
  </tbody>
</table>