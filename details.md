---
title: Details
layout: home
nav_order: 4
---


# Experimental Details on GeFL

## Table I
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
            <th>DCGAN</th>
            <th>CVAE</th>
            <th>DDPM w=0</th>
            <th>DDPM w=2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Optimizer</td>
            <td>SGD</td>
            <td>SGD</td>
            <td>SGD</td>
            <td>SGD</td>
        </tr>
        <tr>
            <td>Learning rate <i>α</i></td>
            <td>0.1</td>
            <td>0.1</td>
            <td>0.1</td>
            <td>0.1</td>
        </tr>
        <tr>
            <td>Communication rounds for training target network<i>T<sub>TN</sub></i></td>
            <td>100</td>
            <td>100</td>
            <td>100</td>
            <td>100</td>
        </tr>
        <tr>
            <td>Local epochs for training training target network by real samples <i>T<sub>r</sub></i></td>
            <td>5</td>
            <td>5</td>
            <td>5</td>
            <td>5</td>
        </tr>
        <tr>
            <td>Local epochs for training training target network by synthetic samples <i>T<sub>s</sub></i></td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
        </tr>
        <tr>
            <td>Batch size <i>B</i></td>
            <td>128</td>
            <td>128</td>
            <td>128</td>
            <td>128</td>
        </tr>
    </tbody>
</table>

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
            <th>DCGAN</th>
            <th>CVAE</th>
            <th>DDPM w=0</th>
            <th>DDPM w=2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Optimizer</td>
            <td>SGD</td>
            <td>SGD</td>
            <td>SGD</td>
            <td>SGD</td>
        </tr>
        <tr>
            <td>Learning rate <i>α</i></td>
            <td>0.1</td>
            <td>0.1</td>
            <td>0.1</td>
            <td>0.1</td>
        </tr>
        <tr>
            <td>Communication rounds for training target network<i>T<sub>TN</sub></i></td>
            <td>100</td>
            <td>100</td>
            <td>100</td>
            <td>100</td>
        </tr>
        <tr>
            <td>Local epochs for training training target network by real samples <i>T<sub>r</sub></i></td>
            <td>5</td>
            <td>5</td>
            <td>5</td>
            <td>5</td>
        </tr>
        <tr>
            <td>Local epochs for training target network by synthetic samples <i>T<sub>s</sub></i></td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
        </tr>
        <tr>
            <td>Batch size <i>B</i></td>
            <td>64</td>
            <td>64</td>
            <td>64</td>
            <td>64</td>
        </tr>
    </tbody>
</table>

## Table II

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

## Table III
- Generative model: DCGAN
- All the parameters settings are identical to Table 1

Note: DA techniques are used only during target network training (not in training generative models) 


## Figure 5
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
            <th>DCGAN</th>
            <th>CVAE</th>
            <th>DDPM w=0</th>
            <th>DDPM w=2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Optimizer</td>
            <td>SGD</td>
            <td>SGD</td>
            <td>SGD</td>
            <td>SGD</td>
        </tr>
        <tr>
            <td>Learning rate <i>α</i></td>
            <td>0.1</td>
            <td>0.1</td>
            <td>0.1</td>
            <td>0.1</td>
        </tr>
        <tr>
            <td>Communication rounds for warming up feature extractor<i>T<sub>FE</sub></i></td>
            <td>50</td>
            <td>50</td>
            <td>50</td>
            <td>50</td>
        </tr>
        <tr>
            <td>Local epochs for training feature extractor <i>T<sub>w</sub></i></td>
            <td>5</td>
            <td>5</td>
            <td>5</td>
            <td>5</td>
        </tr>
        <tr>
            <td>Communication rounds for training target network<i>T<sub>TN</sub></i></td>
            <td>100</td>
            <td>100</td>
            <td>100</td>
            <td>100</td>
        </tr>
        <tr>
            <td>Local epochs for training target network by real samples <i>T<sub>r</sub></i></td>
            <td>5</td>
            <td>5</td>
            <td>5</td>
            <td>5</td>
        </tr>
        <tr>
            <td>Local epochs for training target network by synthetic samples <i>T<sub>s</sub></i></td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
        </tr>
        <tr>
            <td>Batch size <i>B</i></td>
            <td>128</td>
            <td>128</td>
            <td>128</td>
            <td>128</td>
        </tr>
    </tbody>
</table>

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
    <caption>Target network (CNN) parameters</caption>
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
            <td>SGD</td>
            <td>SGD</td>
            <td>SGD</td>
            <td>SGD</td>
        </tr>
        <tr>
            <td>Learning rate <i>α</i></td>
            <td>0.1</td>
            <td>0.1</td>
            <td>0.1</td>
            <td>0.1</td>
        </tr>
        <tr>
            <td>Communication rounds for warming up feature extractor<i>T<sub>FE</sub></i></td>
            <td>20</td>
            <td>20</td>
            <td>20</td>
            <td>20</td>
        </tr>
        <tr>
            <td>Local epochs for training feature extractor <i>T<sub>w</sub></i></td>
            <td>5</td>
            <td>5</td>
            <td>5</td>
            <td>5</td>
        </tr>
        <tr>
            <td>Communication rounds for training target network<i>T<sub>TN</sub></i></td>
            <td>50</td>
            <td>50</td>
            <td>50</td>
            <td>50</td>
        </tr>
        <tr>
            <td>Local epochs for training target network by real samples <i>T<sub>r</sub></i></td>
            <td>5</td>
            <td>5</td>
            <td>5</td>
            <td>5</td>
        </tr>
        <tr>
            <td>Local epochs for training target network by synthetic samples <i>T<sub>s</sub></i></td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
        </tr>
        <tr>
            <td>Batch size <i>B</i></td>
            <td>64</td>
            <td>64</td>
            <td>64</td>
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
  - Total 10 results for each dataset 
  - Other parameters are identical to Table 1 

## Table 8

- Same as Table 7 