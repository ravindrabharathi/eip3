



## ***Ravindra Bharathi*** 

### *email:srbharathee@gmail.com , EIP3 Batch 6*

### ***<u>Assignment 1C</u>*** 

### Convolution

Convolution is a technique used in image and signal processing. In image processing by running or sliding a filter over an image (which can be considered as a 2D signal with 1 or more color channels) , we can achieve various outcomes like blurring, noise reduction, edge detection, sharpening, etc. In deep learning this concept is used in convolutional neural networks (CNN) to extract features from a signal or image. In CNN, several convolutional layers are used as hidden layers to extract and learn features of an image.

![convolution](https://raw.githubusercontent.com/ravindrabharathi/eip3/master/images/convolution.png)

### Filters/Kernels

Filters or Kernels are used in convolutional neural networks to detect features in images and signals. So a kernel is also called a feature detector. In order to detect features in an image  a 2D filter of size nxn where n is typically odd is used. The most common filter is of size 3x3.  Sliding a 3x3 filter over a nxn size image results in a convolved layer or image that is of size n-2 x n-2. Every convolution layer in a CNN progressively learns more complex patterns in an image.

![3x3 filter on MNIST data](https://raw.githubusercontent.com/ravindrabharathi/eip3/master/images/3x3_filteron_Mnist.png)

[^]:                          A 3x3 filter learning features of an MNIST image sample 

### Epochs 

In deep learning an epoch represents a run on the complete training set consisting of a forward pass and a back propagation(which updates the weights). A network may run several epochs until it is able to learn enough to minimise the loss and converge to a global minimum. Typically training continues until such time where further training would not reduce validation loss any more. Training beyond such points results in overfitting the model and the model will not generalize well for data that it has not seen before. 

### Activation Function

Activation functions are applied to the nodes in a neural network to decide whether that particular node will contribute forward to the next layer (if > threshold value) or not i.e if that particular node is important for the feature being learnt. An activation function adds non-linearity to the network which enables the network to learn more complex functions. There are several activation functions like step function, sigmoid , tanh , ReLU , Softmax, etc. The most popular activation function used in hidden layers is ReLU and for the output layers it is typically Softmax (multiclass classifier) or Sigmoid (binary classification)

![ReLU activation function](https://raw.githubusercontent.com/ravindrabharathi/eip3/master/images/ReLU.png)

### ` 3x3 convolution

3x3 convolution is the technique used in CNN where a 3x3 filter/kernel slides over an image (a 2D matrix of pixels (times 1 channel for greyscale , 3 channels for RGB, etc)) to extract features like edges initially and progressively more complex features like textures,patterns,parts of objects, objects as we go deeper into the neural network. 3x3 convolution is widely used as it helps you efficiently learn information with a lesser number of parameters. A convolution layer will have a number a channels with each channel being a container for features of similar nature e.g vertical edges
<math xmlns="http://www.w3.org/1998/Math/MathML" display="block">
  <mrow>
    <mo>[</mo>
    <mtable rowspacing="4pt" columnspacing="1em">
      <mtr>
        <mtd>
          <mn>1</mn>
        </mtd>
        <mtd>
          <mn>1</mn>
        </mtd>
        <mtd>
          <mn>0</mn>
        </mtd>
        <mtd>
          <mn>0</mn>
        </mtd>
        <mtd>
          <mn>1</mn>
        </mtd>
      </mtr>
      <mtr>
        <mtd>
          <mn>1</mn>
        </mtd>
        <mtd>
          <mn>0</mn>
        </mtd>
        <mtd>
          <mn>1</mn>
        </mtd>
        <mtd>
          <mn>0</mn>
        </mtd>
        <mtd>
          <mn>1</mn>
        </mtd>
      </mtr>
      <mtr>
        <mtd>
          <mn>0</mn>
        </mtd>
        <mtd>
          <mn>1</mn>
        </mtd>
        <mtd>
          <mn>1</mn>
        </mtd>
        <mtd>
          <mn>0</mn>
        </mtd>
        <mtd>
          <mn>0</mn>
        </mtd>
      </mtr>
      <mtr>
        <mtd>
          <mn>1</mn>
        </mtd>
        <mtd>
          <mn>1</mn>
        </mtd>
        <mtd>
          <mn>1</mn>
        </mtd>
        <mtd>
          <mn>1</mn>
        </mtd>
        <mtd>
          <mn>1</mn>
        </mtd>
      </mtr>
      <mtr>
        <mtd>
          <mn>1</mn>
        </mtd>
        <mtd>
          <mn>1</mn>
        </mtd>
        <mtd>
          <mn>0</mn>
        </mtd>
        <mtd>
          <mn>0</mn>
        </mtd>
        <mtd>
          <mn>1</mn>
        </mtd>
      </mtr>
    </mtable>
    <mo>]</mo>
  </mrow>
  <mo>&#x2217;<!-- ∗ --></mo>
  <mrow>
    <mo>[</mo>
    <mtable rowspacing="4pt" columnspacing="1em">
      <mtr>
        <mtd>
          <mn>1</mn>
        </mtd>
        <mtd>
          <mn>0</mn>
        </mtd>
        <mtd>
          <mo>&#x2212;<!-- − --></mo>
          <mn>1</mn>
        </mtd>
      </mtr>
      <mtr>
        <mtd>
          <mn>1</mn>
        </mtd>
        <mtd>
          <mn>0</mn>
        </mtd>
        <mtd>
          <mo>&#x2212;<!-- − --></mo>
          <mn>1</mn>
        </mtd>
      </mtr>
      <mtr>
        <mtd>
          <mn>1</mn>
        </mtd>
        <mtd>
          <mn>0</mn>
        </mtd>
        <mtd>
          <mo>&#x2212;<!-- − --></mo>
          <mn>1</mn>
        </mtd>
      </mtr>
    </mtable>
    <mo>]</mo>
  </mrow>
  <mspace linebreak="newline" />
  <mstyle mathcolor="#C00">
    <mrow class="MJX-TeXAtom-ORD">
      <mo stretchy="false">|</mo>
    </mrow>
    <mrow class="MJX-TeXAtom-ORD">
      <mo stretchy="false">|</mo>
    </mrow>
  </mstyle>
  <mspace linebreak="newline" />
  <mstyle mathcolor="#C00">
    <mrow>
      <mo>[</mo>
      <mtable rowspacing="4pt" columnspacing="1em">
        <mtr>
          <mtd>
            <mrow>
              <mo>(</mo>
              <mtable rowspacing="4pt" columnspacing="1em">
                <mtr>
                  <mtd>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mo>+</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mo>+</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
              </mtable>
              <mo>)</mo>
            </mrow>
            <mrow>
              <mo>(</mo>
              <mtable rowspacing="4pt" columnspacing="1em">
                <mtr>
                  <mtd>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mo>+</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mo>+</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
              </mtable>
              <mo>)</mo>
            </mrow>
            <mrow>
              <mo>(</mo>
              <mtable rowspacing="4pt" columnspacing="1em">
                <mtr>
                  <mtd>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mo>+</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mo>+</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
              </mtable>
              <mo>)</mo>
            </mrow>
          </mtd>
        </mtr>
        <mtr>
          <mtd />
        </mtr>
        <mtr>
          <mtd>
            <mrow>
              <mo>(</mo>
              <mtable rowspacing="4pt" columnspacing="1em">
                <mtr>
                  <mtd>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mo>+</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mo>+</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
              </mtable>
              <mo>)</mo>
            </mrow>
            <mrow>
              <mo>(</mo>
              <mtable rowspacing="4pt" columnspacing="1em">
                <mtr>
                  <mtd>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mo>+</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mo>+</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
              </mtable>
              <mo>)</mo>
            </mrow>
            <mrow>
              <mo>(</mo>
              <mtable rowspacing="4pt" columnspacing="1em">
                <mtr>
                  <mtd>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mo>+</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mo>+</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
              </mtable>
              <mo>)</mo>
            </mrow>
          </mtd>
        </mtr>
        <mtr>
          <mtd />
        </mtr>
        <mtr>
          <mtd>
            <mrow>
              <mo>(</mo>
              <mtable rowspacing="4pt" columnspacing="1em">
                <mtr>
                  <mtd>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mo>+</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mo>+</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
              </mtable>
              <mo>)</mo>
            </mrow>
            <mrow>
              <mo>(</mo>
              <mtable rowspacing="4pt" columnspacing="1em">
                <mtr>
                  <mtd>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mo>+</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mo>+</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
              </mtable>
              <mo>)</mo>
            </mrow>
            <mrow>
              <mo>(</mo>
              <mtable rowspacing="4pt" columnspacing="1em">
                <mtr>
                  <mtd>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mo>+</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mo>+</mo>
                  </mtd>
                </mtr>
                <mtr>
                  <mtd>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>1</mn>
                    <mo>+</mo>
                    <mn>0</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mn>0</mn>
                    <mo>+</mo>
                    <mo stretchy="false">(</mo>
                    <mn>1</mn>
                    <mo>&#x2217;<!-- ∗ --></mo>
                    <mo>&#x2212;<!-- − --></mo>
                    <mn>1</mn>
                    <mo stretchy="false">)</mo>
                  </mtd>
                </mtr>
              </mtable>
              <mo>)</mo>
            </mrow>
          </mtd>
        </mtr>
      </mtable>
      <mo>]</mo>
    </mrow>
  </mstyle>
  <mspace linebreak="newline" />
  <mstyle mathcolor="#00F">
    <mrow class="MJX-TeXAtom-ORD">
      <mo stretchy="false">|</mo>
    </mrow>
    <mrow class="MJX-TeXAtom-ORD">
      <mo stretchy="false">|</mo>
    </mrow>
  </mstyle>
  <mspace linebreak="newline" />
  <mstyle mathcolor="#00F">
    <mrow>
      <mo>[</mo>
      <mtable rowspacing="4pt" columnspacing="1em">
        <mtr>
          <mtd>
            <mn>0</mn>
          </mtd>
          <mtd>
            <mn>2</mn>
          </mtd>
          <mtd>
            <mn>0</mn>
          </mtd>
        </mtr>
        <mtr>
          <mtd>
            <mo>&#x2212;<!-- − --></mo>
            <mn>1</mn>
          </mtd>
          <mtd>
            <mn>1</mn>
          </mtd>
          <mtd>
            <mn>1</mn>
          </mtd>
        </mtr>
        <mtr>
          <mtd>
            <mn>1</mn>
          </mtd>
          <mtd>
            <mn>2</mn>
          </mtd>
          <mtd>
            <mn>0</mn>
          </mtd>
        </mtr>
      </mtable>
      <mo>]</mo>
    </mrow>
  </mstyle>
  <mspace linebreak="newline" />
</math>

[^]:                                             3x3 filter applied to a 5x5 image matrix resulting in a 3x3 convolved output

