# Image Style Transfer with Deep Neural Networks

## Table of Contents

* [Description](#description)
* [Tools & Dependencies](#tools)
* [Installation](#installation)
* [Contributing](#contributing)
* [License](#license)

## Description

In this notebook, I’ll *recreate* a style transfer method that is outlined in the paper, [Image Style Transfer Using Convolutional Neural Networks, by Gatys](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf) in PyTorch. This exercise is part of the [Udacity's](https://udacity.com/) Deep Learning nanodegree. Exercise template can be downloaded from the Udacity's GitHub site - [here](https://github.com/udacity/deep-learning-v2-pytorch/blob/master/style-transfer/Style_Transfer_Exercise.ipynb).

In this paper, style transfer uses the features found in the 19-layer VGG Network, which is comprised of a series of convolutional and pooling layers, and a few fully-connected layers. In the image below, the convolutional layers are named by stack and their order in the stack. Conv_1_1 is the first convolutional layer that an image is passed through, in the first stack. Conv_2_1 is the first convolutional layer in the *second* stack. The deepest convolutional layer in the network is conv_5_4.

<img src='images/vgg19_convlayers.png' width=80% />

### Separating Style and Content

Style transfer relies on separating the content and style of an image. Given one content image and one style image, I aim to create a new, _target_ image which should contain the desired content and style components:
* objects and their arrangement are similar to that of the **content image**
* style, colors, and textures are similar to that of the **style image**

An example is shown below, where the content image is of a cat, and the style image is of [Hokusai's Great Wave](https://en.wikipedia.org/wiki/The_Great_Wave_off_Kanagawa). The generated target image still contains the cat but is stylized with the waves, blue and beige colors, and block print textures of the style image!

<img src='images/style_tx_cat.png' width=80% />

In this notebook, I'll use a pre-trained VGG19 Net to extract content or style features from a passed in image. I'll then formalize the idea of content and style _losses_ and use those to iteratively update my target image until I get a result that I want.

## Tools & Dependencies

The data in this repository comes from Udacity's GitHub site - [here](https://github.com/udacity/deep-learning-v2-pytorch/blob/master/style-transfer/Style_Transfer_Exercise.ipynb).

The project has been built in the [Jupyter Notebook](http://jupyter.org/), using Python 3.x, Torch v.0.4.1 and Torchvision v.0.2.1. Detail list of required libraries can be found in the `requirements.txt`.

## Installation

To run this project:
  
1. With python 3.x installed, create a virtual environment and activate it as shown:
  
```shell
  virtualenv -p python3 my_virtualenv
  source my_virtualenv/bin/activate
```
2. Clone this repository into your virtual environment:  

```shell
git clone https://github.com/BarbaraStempien/DL--Image-Style-Transfer.git
```
3. Install project dependencies:  

```shell
pip install -r DL--Image-Style-Transfer/requirements.txt
```
  
4. Open Jupter Notebook, and run the project.

## Contributing

I accept contributions. For details, check out [CONTRIBUTING.md](CONTRIBUTING.md).

## License

[MIT License](LICENSE)

Copyright (c) 2018 Barbara Stempien

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
