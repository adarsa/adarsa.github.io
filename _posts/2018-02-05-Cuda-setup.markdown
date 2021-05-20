---
layout: post
title:  "CUDA setup for Tensorflow"
date:   2018-02-05 19:45:02 +0530
categories: python
tags:
  - CUDA
  - Python
  - Tensorflow
  - GPU
---

Though I had used Tensorflow before, it was mostly for small-scale computations. When we decided to step up and use DNN's for our day-to-day work on the Sunbird platform, I had to set up Tensorflow in a GPU-enabled system. The TensorFlow documentation is pretty user-friendly (Ref: [TensorFlow documentation](https://www.tensorflow.org/install/install_sources)).

Edit: [Updated link]((https://www.tensorflow.org/install/gpu#older_versions_of_tensorflow))


If you are installing for a single user non-distributed system, you can install directly using pip. If you are worried about dependencies with your existing packages, it is better to set up a virtual environment and install TensorFlow.

Prerequisites: 
Cuda toolkit:
Ref: [Cuda installation guide](http://developer2.download.nvidia.com/compute/machine-learning/cudnn/secure/v7.0.5/prod/Doc/cuDNN-Installation-Guide.pdf?1w636cWGqVbJ7HORdjFprwHIJgCAqJsl24Jx79FsEvGKiV0rV96NBY8a7bXxZgsUW1P59K4gXeUYdoQq4xgg-adElyc0okvS0vxZsYsSEU70KCTJbyb98IEpaFuglQaFHkl0wTXI9QOVR7_NzertXrWDETMK7x9yapD9u-rAwh30We1PGk-NUKo9e0APV0PUjQ)

Edit: [Updated link](https://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html)

The current version of Cuda is 9.1. Note that this version of CUDA with the latest version of CudNN is not supported by the version of TensorFlow. So you would require to build tf from source if you go with Cuda 9.1. The steps are described in the TensorFlow installation step.

#### 1.1 Verify you have a CUDA-Capable GPU
```
	Run : lspci | grep -i nvidia. 
```
If you do not see any settings, update the PCI hardware database that Linux maintains by entering ```update-pciids``` (generally found in /sbin) at the command line and rerun the previous ```lspci``` command.

#### 1.2. Verify You Have a Supported Version of Linux
The CUDA Development Tools are only supported on some specific distributions of Linux. These are listed in the CUDA Toolkit release notes.
To determine which distribution and release number you're running, type the following at the command line:

```
$ uname -m && cat /etc/*release
```
You should see output similar to the following, modified for your particular system:
```
x86_64
Red Hat Enterprise Linux Workstation release 6.0 (Santiago)
```
The x86_64 line indicates you are running on a 64-bit system. The remainder gives information about your distribution.

#### 1.3 Verify the System Has gcc Installed
 
```
gcc --version
```

#### 1.4 Verify the System has the Correct Kernel Headers and Development Packages Installed

``` uname -r```
This is the current version of kernal head. The kernel headers and development packages for the currently running kernel can be installed with:
```
$ sudo apt-get install linux-headers-$(uname -r)
```
#### 1.5 . Download the NVIDIA CUDA Toolkit
The NVIDIA CUDA Toolkit is available at http://developer.nvidia.com/cuda-downloads.
The documents  mentions that download can be verified by running ```md5sum <file>.``` This is not updated for latest OS versions.
Uninstall previous versions before install:
```
sudo /usr/local/cuda-X.Y/bin/uninstall_cuda_X.Y.pl
sudo /usr/bin/nvidia-uninstall
```

For deb installation:
```
sudo apt-get --purge remove <package_name>      
```
1.6 Install:
```
sudo dpkg -i cuda-repo-<distro>_<version>_<architecture>.deb
```
Installing the CUDA public GPG key
When installing using the local repo:
```
sudo apt-key add /var/cuda-repo-<version>/7fa2af80.pub
```
OR if you do not have matching deb file downloaded, install using network repo:
```
sudo apt-key adv --fetch-keys https://developer.download.nvidia.com/compute/cuda/repos/<distro>/<architecture>/7fa2af80.pub
```

Update the Apt repository cache
```
sudo apt-get update
```

Install CUDA
```
sudo apt-get install cuda
```
#### 1.7 Package update 
```
sudo apt-get install cuda 
sudo apt-get install cuda-drivers
```
NOTE: The CUDA installation describes runfile installation with disabling Nouveau drivers.The latest version of TF do not require this. A simple deb installation lets your life remain simple!

The NVIDIA drivers associated with CUDA Toolkit 8.0

If you have downloaded the NVIDIA CUDA toolkit, the installation step woulds have done the installation for your drivers and you do not have to do any other installation ([Install cuDNN v6.0](https://www.tensorflow.org/install/install_linux#NVIDIARequirements
)) 
