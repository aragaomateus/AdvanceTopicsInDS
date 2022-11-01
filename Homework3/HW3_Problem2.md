
# Problem 2 - Convolutional Neural Networks Architectures 35 points
In this problem we will study and compare different convolutional neural network architectures. We will calculate number of parameters (weights, to be learned) and memory requirement of each network. We will also analyze inception modules and understand their design.

• (Alexnet) Alex Krizhevsky et al. ImageNet Classification with Deep Convolutional Neural Networks. Paper available at https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional- neural-networks.pdf
• (VGG) Karen Simonyan et al. Very Deep Convolutional Networks for Large-scale Image Recognition. Paper available at https://arxiv.org/pdf/1409.1556.pdf
• (Googlenet) Christian Szegedy et al. Going deeper with convolutions. Paper available at https://arxiv.org/pdf/1409.4842.pdf

1. Calculate the number of parameters in Alexnet. You will have to show calculations for each layer and then sum it to obtain the total number of parameters in Alexnet. When calculating you will need to account for all the filters (size, strides, padding) at each layer. Look at Sec. 3.5 and Figure 2 in Alexnet paper (see reference). Points will only be given when explicit calculations are shown for each layer. (4)

***Answer:***

Input|Layer|Stride|Pad|Kernel Size| In |Out| Number of Parameters|
-----|-----|------|---|-----------|----|---|---------------------|
(227,227,3)|conv1|4|0  |(11,11)|3|96|(11*11)*3*96 + 96 = 34944|
(55,55,96)|maxpool1|2|0|(3,3)  |96|96|0|
(27,27,96)|conv2|1|2|(5,5)|96|256| (5*5)*96*256 + 256 = 614656|
(27,27,256)|maxpool2|2|0|(3,3)|256|256|0|
(13,13,256)|conv3|1|1|(3,3)|256|384|(3*3)*256*384 + 384 = 885120|
(13,13,384)|conv4|1|1|(3,3)|384|384|(3*3)*384*384 + 384 = 1327488|
(13,13,384)|conv4|1|1|(3,3)|384|256|conv5: (3*3)*384*256 + 256 = 884992|
(13,13,256)|maxpool2|2|0|(3,3)|256|256|0|
|fc6|||(1,1)|256|4096|(6*6)*256*4096 + 4096 = 37752832|
|fc7|||(1,1)|4096|4096|4096*4096 + 4096 = 16781312|
|fc8|||(1,1)|4096|4096| 4096*1000 + 1000 = 4097000|
Total|62,378,344|








2. VGG (Simonyan et al.) has an extremely homogeneous architecture that only performs 3x3 convolutions with stride 1 and pad 1 and 2x2 max pooling with stride 2 (and no padding) from the beginning to the end. However VGGNet is very expensive to evaluate and uses a lot more memory and parameters. Refer to VGG19 architecture on page 3 in Table 1 of the paper by Simonyan et al. You need to complete Table 1 below for calculating activation units and parameters at each layer in VGG19 (without counting biases). Its been partially filled for you. (6)

***Answer:***

Layers|Number of activiations | Parameters|
------|-----------------------|-----------|
Input |224* 224 *3=150K|0
CONV3-64|224 * 224*64=3.2M|(3* 3* 3)*64 =1792
CONV3-64|224 *224 *64=3.2M|(3* 3* 64)*64=36928
POOL2|112* 112* 64=800K|0
CONV3-128|112* 112* 128=1.6M|(3 *3* 64)*128 =73856
CONV3-128|112* 112* 128=1.6M|(3* 3* 128)*128 =147584
POOL2|56* 56* 128=400K |0
CONV3-256|56* 56* 256=800K|(3* 3* 128)*256 295168
CONV3-256|56* 56* 256=800K|(3* 3* 256)*256 =590080
CONV3-256|56* 56* 256=800K|(3* 3* 256)*256 =590080
POOL2|28* 28* 256=200K|0
CONV3-512|28* 28* 512=400K|(3* 3* 256)*512=1180160
CONV3-512|28* 28* 512=400K|(3* 3* 512)*512=2359808
CONV3-512|28* 28* 512=400K|(3* 3* 512)*512 =2359808
POOL2|14* 14* 512=100K|0
CONV3-512|14* 14* 512=100K|(3* 3* 512)*512 =2359808
CONV3-512|14* 14* 512=100K|(3* 3* 512)*512 =2359808
CONV3-512|14* 14* 512=100K|(3* 3* 512)*512 =2359808
POOL2|7* 7* 512=25K |0
FC|4096|7* 7* 512* 4096 = 102764544
FC|4096|4096 *4096 = 16,777,216
FC|1000|4096 *1000 = 4097000
Total|| 138,357,544

3. VGG architectures have smaller filters but deeper networks compared to Alexnet (3x3 compared to 11x11 or 5x5). Show that a stack of N convolution layers each of filter size F × F has the same receptive field as one convolution layer with filter of size (NF − N + 1) × (NF − N + 1). Use this to calculate the receptive field of 3 filters of size 5x5. (3)

***Answer:***

If we use a stack of 3 convolutional layers of kernel size equal (5,5) we will get a receptive field of (13x13).

with N =3 and F=5:
(N* F - N +1) X (N* F - N +1) = 

(3* 5 - 3 +1) X (3* 5 - 3 +1) = 

(15 - 3 +1) X (15- 3 +1) =  (15 - 3 +1) X (15- 3 +1) = (13x13) 


4. The original Googlenet paper (Szegedy et al.) proposes two architectures for Inception module, shown in Figure 2 on page 5 of the paper, referred to as naive and dimensionality reduction respectively.

(a) What is the general idea behind designing an inception module (parallel convolutional filters of different sizes with a pooling followed by concatenation) in a convolutional neural network ? (2)
***Answer:***

(b) Assuming the input to inception module (referred to as ”previous layer” in Figure 2 of the paper) has size 32x32x256, calculate the output size after filter concatenation for the naive and dimensionality reduction inception architectures with number of filters given in Figure 1. (3)

***Answer:***
Naive inception:

1x1 convolutions, 128 filters 

3x3 convolutions, 192 filters 

5x5 convolutions, 96 filters  

3x3 max pooling,256  

= 32x32x(128 + 192 + 96 +256) = 672 output


Dimentionality reduction inception:

1x1 convolutions , 128 filters 

1x1 convolutions 64 filters +
3x3 convolutions ,192 filters

1x1 convolutions , 64 filters +
5x5 convolutions  , 96 filters

3x3 max pooling, 256 filters + 
1x1 convolutions  ,64 filters

= 32x32x480 output

(c) Next calculate the total number of convolutional operations for each of the two inception architecture again assuming the input to the module has dimensions 32x32x256 and number of filters given in Figure 1. (3)

***Answer:***

Naive inception:

1x1 convolutions, 128 filters 

computation = (32 *32) * 128 * (1 *1) *256 = 33,554,432

3x3 convolutions, 192 filters 
computation = (32 *32) * 192 * (3 *3) *256 = 452,884,832

5x5 convolutions, 96 filters 
computation = (32 *32) * 96 * (5 *5) *256 = 629,145,600

3x3 max pooling,256 filters

computation = 0

Total = 1.11 Billion computations


Dimentionality reduction inception:

1x1 convolutions , 128 filters 
Computations= (32 *32) * 128 * (1 *1) *256 = 33,554,432

1x1 convolutions 64 filters +
3x3 convolutions ,192 filters
Computations= (32 *32) * 64 * (1 *1)*256

 $+$ (32 *32) * 192 * (3 *3) * 64 = 130,023,424

1x1 convolutions , 64 filters +
5x5 convolutions  , 96 filters

Computations= (32 *32) * 64 * (1 *1)*256

$+$ (32 *32) * 96 * (5 *5) * 64 = 174,063,616

3x3 max pooling , 256 filters+ 
1x1 convolutions  ,64 filters

Computations= (32 *32) * 64 * (1 *1) *64 =  4,194,304
total computation = 341,835,776

(d) Based on the calculations in part (c) explain the problem with naive architecture and how dimen- sionality reduction architecture helps (Hint: compare computational complexity). How much is the computational saving ? 

***Answer:***

1.11billion - 341,835,776 $\approx$ 770 millions computations were saved.

5. Faster-RCNN is a CNN based architecture for object detection which is much faster that Fast-RCNN. Read about Faster-RCNN in Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks and answer the following questions:

(a) What is the main difference between Fast-RCNN and Faster-RCNN that resulted in faster detection using Faster-RCNN? (2)

(b) What is Region Proposal Network (RPN)? Clearly explain its architecture. (2)

(c) Explain how are region proposals generated from RPN using an example image.(3)

(d) There is a lot of overlap in the region proposals generated by RPN. What technique is used in Faster-RCNN to reduce the number of proposals to roughly 2000? Explain how does this technique work using an example. (3)