# mxnet-for-jetson-ubuntu20.04_python3.8

Follow the following steps to install the mxnet on jetson nano with ubuntu20.04 that comes with Python 3.8

1. Download the file from lin below:
https://drive.google.com/file/d/1ctjtpgptV3z4lA-akxX8Uturh4K8mqUl/view?usp=share_link

2. Download mxnet-1.8.0 source files from link below:
https://github.com/apache/mxnet/releases/tag/1.8.0

3. Merge above two downloads

4. Install the following dependencies
sudo apt-get update
sudo apt-get install -y \
                        build-essential \
                        git \
                        libopenblas-dev \
                        libopencv-dev \
                        python3-pip \
                        python-numpy

sudo pip3 install --upgrade \
                        pip \
                        setuptools \
                        numpy
                        
5. $ cd mxnet/python
   $ sudo pip3 install -e .

6. Test the installation
$ python3
import mxnet
mxnet.__version__

This shoould show: '1.8.0'


7. Test gpu:
import mxnet as mx
a = mx.nd.ones((2, 3), mx.gpu())
b = a * 2 + 1
b.asnumpy()

array([[3., 3., 3.],
       [3., 3., 3.]], dtype=float32)
b

[[3. 3. 3.]
 [3. 3. 3.]]
<NDArray 2x3 @gpu(0)>


Prerequisits:
Jetson Nano 4GB
Jetpack: Qengineering Ubuntu 20.04


References:
[1]. https://mxnet.apache.org/get_started/jetson_setup

