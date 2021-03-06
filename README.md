# PyCNN: Image Processing with Cellular Neural Networks in Python

**Cellular Neural Networks (CNN)** [[wikipedia]](https://en.wikipedia.org/wiki/Cellular_neural_network) [[paper]](http://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=7600) are a parallel computing paradigm that was first proposed in 1988. Cellular neural networks are similar to neural networks, with the difference that communication is allowed only between neighboring units. Image Processing is one of its [applications](https://en.wikipedia.org/wiki/Cellular_neural_network#Applications). CNN processors were designed to perform image processing; specifically, the original application of CNN processors was to perform real-time ultra-high frame-rate (>10,000 frame/s) processing unachievable by digital processors.

This python library is the implementation of CNN for the application of **Image Processing**.

**Note**: The library has been **cited** in the research published on [Using Python and Julia for Efficient Implementation of Natural Computing and Complexity Related Algorithms](http://ieeexplore.ieee.org/xpl/articleDetails.jsp?arnumber=7168488), look for the reference #19 in the references section. I'm glad that this library could be of help to the community.

**Note**: Cellular neural network (CNN) must not be confused with completely different convolutional neural network (ConvNet).

![alt text](http://www.isiweb.ee.ethz.ch/haenggi/CNN_web/CNN_figures/blockdiagram.gif "CNN Architecture")

As shown in the above diagram, imagine a control system with a feedback loop. f(x) is the sigmoidal kernel function for this system. The control and the feedback templates (coefficients) are configurable and controls the output of the system. Significant research had been done in determining the templates for common image processing techniques, these templates are published in this [Template Library](http://cnn-technology.itk.ppke.hu/Template_library_v4.0alpha1.pdf).

## Motivation

This is an extension of a demo at 14th Cellular Nanoscale Networks and Applications (CNNA) Conference 2014. I have written a blog post, available at [Image Processing in CNN with Python on Raspberry Pi](http://blog.ankitaggarwal.me/technology/image-processing-with-cellular-neural-networks-using-python-on-raspberry-pi/).

## Dependencies

The library is supported for Python >= 2.7 and Python >= 3.3.

The python modules needed in order to use this library.
```
Pillow: 3.3.1
Scipy: 0.18.0
Numpy: 1.11.1 + mkl
```
Note: Scipy and Numpy can be installed on a Windows machines using binaries provided over [here](http://www.lfd.uci.edu/%7Egohlke/pythonlibs).

## Usage
*Image Processing* using CNN is simple using this library, just clone the repository and use the following code.
```python
from pycnn import pycnn

cnn = pycnn()

cnn.edgedetection('input.bmp', 'output1.png')
cnn.grayscaleedgedetection('input.bmp', 'output2.png')
cnn.cornerdetection('input.bmp', 'output3.png')
cnn.diagonallinedetection('input.bmp', 'output4.png')
cnn.inversion('input.bmp', 'output5.png')
cnn.generaltemplates('input.bmp', 'output6.png')
```
#### OR
Use example.py available with the repository.
```sh
$ python example.py
```

## Example results

![](https://raw.githubusercontent.com/ankitaggarwal011/PyCNN/master/images/input.bmp)
*Input: input.bmp*

**Edge Detection:**

![](https://raw.githubusercontent.com/ankitaggarwal011/PyCNN/master/images/output1.png)
*Output: output1.png*


**Corner Detection:**

![](https://raw.githubusercontent.com/ankitaggarwal011/PyCNN/master/images/output3.png)
*Output: output3.png*


**Diagonal line Detection:**

![](https://raw.githubusercontent.com/ankitaggarwal011/PyCNN/master/images/output4.png)
*Output: output4.png*


**Inversion (Logic NOT):**

![](https://raw.githubusercontent.com/ankitaggarwal011/PyCNN/master/images/output5.png)
*Output: output5.png*

## Another example (Lenna)

Here, the input is the popular face in image processing field, Lenna.

![](https://raw.githubusercontent.com/ankitaggarwal011/PyCNN/master/images/lenna.gif)
*Input: lenna.gif*


**Edge Detection:**

![](https://raw.githubusercontent.com/ankitaggarwal011/PyCNN/master/images/lenna_edge.png)
*Output: lenna_edge.png*


**Diagonal line Detection:**

![](https://raw.githubusercontent.com/ankitaggarwal011/PyCNN/master/images/lenna_diagonal.png)
*Output: lenna_diagonal.png*


## API
```python
from pycnn import pycnn
```
Import the module in your main file.

```python
cnn = pycnn()
```
Initialize the cnn class

#### cnn.edgedetection(inputimagelocation, outputimagelocation)
Function for edge detection using CNN on a given image.
#### cnn.grayscaleedgedetection(inputimagelocation, outputimagelocation)
Function for grayscale edge detection using CNN on a given image.
#### cnn.cornerdetection(inputimagelocation, outputimagelocation)
Function for corner detection using CNN on a given image.
#### cnn.diagonallinedetection(inputimagelocation, outputimagelocation)
Function for diagonal line detection using CNN on a given image.
#### cnn.inversion(inputimagelocation, outputimagelocation)
Function for invert an image using CNN.
#### cnn.generaltemplates(inputimagelocation, outputimagelocation)
Function for applying general CNN templates on a given image.

#### inputimagelocation is the location of the input image, Type: String.
#### outputimagelocation is the location of the output image, Type: String.


## Contributors

#### Author: Ankit Aggarwal

If anybody is interested in working on developing this library, fork and feel free to get in touch with me.

## License

[MIT License](https://github.com/ankitaggarwal011/CNN-Image-Processing/blob/master/LICENSE)
