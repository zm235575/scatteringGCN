# Scattering GCN

## Reference:
*Scattering GCN: overcoming oversmoothness in graph convolutional networks*

## To run the Code
(default:Cora)\
for example run:\
python train.py --hid1 11 --hid2 6  --sct_inx1 1 --sct_inx2 0 --smoo 0.35

citeseer:\
python citeseer.py

pubmed:\
python 

## Details of the parameters
1. `hid1`: the width in channel  <-----<img src="https://render.githubusercontent.com/render/math?math=\boldsymbol{\Phi_{J_1}}">
2. `hid2`: the width in channel  <-----<img src="https://render.githubusercontent.com/render/math?math=\boldsymbol{\Phi_{J_2}}">
3. `weight_decay`:  <-----L2 reg 
4. `l1`:  <-----L1 reg 
5. `epochs`:  <-----Training epochs
6. `sct_inx1`:  <-----the index of first channel, the index order is listed in Tab 3,4,5.
7. `sct_inx2`:  <-----the index of second channel, the index order is listed in Tab 3,4,5.

* * Scattering term
*  * Index = 0 <-----<img src="https://render.githubusercontent.com/render/math?math=\boldsymbol{\Psi_1}">     
*  * Index = 1 <-----<img src="https://render.githubusercontent.com/render/math?math=\boldsymbol{\Psi_2}">   
*  * Index = 2 <-----<img src="https://render.githubusercontent.com/render/math?math=\boldsymbol{\Psi_3}">    
*  * Index = 3 <-----<img src="https://render.githubusercontent.com/render/math?math=\boldsymbol{\Psi_1|\Psi_2}|">  
*  * Index = 4 <-----<img src="https://render.githubusercontent.com/render/math?math=\boldsymbol{\Psi_2|\Psi_3|}">  

8. `dropout`: The dropout setting
9. `smoo`: The graph residual convolution kernel's parameters.


<img src="Figures/Picture1.png" alt="Structure"  width="600">
Figure. Architectures Visualization. Dataset: a) Cora, b) Citeseer, c) Pubmed. The number indicated under each channel signifies the number of neurons associated with it.

## Training curve 
with different <img src="https://render.githubusercontent.com/render/math?math=\alpha"> for graph residual convolution(Cora）\
<img src="Figures/Accu.jpg" alt="Accuracy"  width="600" >

## Running time 
on Citeseer:\
<img src="Figures/cite_gat_sct.png" alt="Citeseer"  width="600">


## Requirement:
pytorch\
cuda\
scipy: for the sparse matrix operation 

## Reference
https://github.com/tkipf/pygcn  \
https://github.com/PetarV-/GAT \
https://github.com/liqimai/Efficient-SSL
