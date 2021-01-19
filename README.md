Download the dataset from: https://www.kaggle.com/alxmamaev/flowers-recognition

<h1>What is Transfer learning?</h1> 
In transfer learning, we use an existing model to solve different but related problems. Basically, we try to exploit what has been learned in one task and improve generalization in another task. We use the model's pre-trained weights or model architecture to solve our problem. In this blog, we are using the pre-trained weights of VGG16 and VGG19, change the output layer and solve a classification problem on the flower dataset.

<h1>Is transfer learning advantageous?</h1>
Yes, it is! Transfer learning saves training time, gives better performance in most cases, and reduces the need for a huge dataset. It isn't a generalized method but helps in solving related problems.

<h1>Any existing Transfer learning methods to start with?</h1>
Keras applications have given users access to architectures such as VGG16, VGG19, RESNET, and a lot more. There are 25+ models available, with mention of their top accuracies on ImageNet classifications, parameters, depth, and size. You can access the models here. Let's explore two models, know-how these architectures are!

<h1>VGG-16</h1>
Published in 2014, VGG16 [Visual Geometry Group - 16] is one of the simplest CNN architectures used in ImageNet competitions. Taking out the ambiguity of filter size, kernel size and padding, VGG16 is structured as follows:
All convolution layers in VGG-16 have
<ul>
<li>Filter size - 3x3</li>
<li>Stride - 1 </li>
<li>Padding - Same</li>
</ul>

All Max-pooling layers in VGG-16 have
<ul><li>Filter size - 2x2 
<li>Stride - 2
</ul>

<h3>2Conv - 1Maxpool - 2Conv - 1Maxpool - 3Conv - 1Maxpool - 3Conv - 1Maxpool - 3Conv - 1Maxpool - 1FC - 1FC - 1FC</h3>

The architecture has 13 convolutional layers followed by 3 fully connected layers, adding up to 16 layers to learn weights and bias parameters and hence the name VGG-16.
<h1>VGG-19</h1>
VGG-19 architecture is very much similar to VGG-16. We have 3 additional convolutional layers for the VGG-16 network. The architecture is as follows:
<h3>2Conv - 1Maxpool - 2Conv - 1Maxpool - 4Conv - 1Maxpool - 4Conv - 1Maxpool - 4Conv - 1Maxpool - 1FC - 1FC - 1FC</h3>

VGG-16 and VGG-19 architectures, due to their depth are slow to train and produce models of very large size. Though the architectures we see here are different, we can create a simple template to perform transfer learning from these models with few lines of code. 
