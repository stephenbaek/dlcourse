# ISE:6380 Deep Learning (University of Iowa)
This repository contains course materials for the University of Iowa course, ISE:6380 Deep Learning, by Prof. [Stephen Baek](http://www.stephenbaek.com). Free of use for non-commercial/commercial purposes.

## 1. &nbsp; Getting Started using Google Colab (Recommended)

TODO: Put instructions here.

## 2. &nbsp; Getting Started using Your Own Computer
Below are instructions for configuring a TensorFlow development environment on your local machine. This step is not necessary for your success in this course. However, if you are already familiar with Python and are willing to try out TensorFlow on your own computer, the following guide may give you an initial direction.

## 2.1. &nbsp; Install Python
If you already have Python installed on your computer, you can skip this section. There are multiple ways to install Python, but the easiest way would be to use [Anaconda](https://www.anaconda.com/) (why do they name everything with a snake?). Visit the [download page](https://www.anaconda.com/products/individual#Downloads) and select an installer that fits your operating system. There's an [official instruction for Anaconda installation](https://docs.anaconda.com/anaconda/install/) and it's pretty easy to follow. Just make sure to [verify your installation](https://docs.anaconda.com/anaconda/install/verify-install/) at the end.

Before you move on to the next step, open terminal (Linux/Mac) or command prompt (Windows) and make sure you can run the following command without an error:
```bash
conda list
```

## 2.2. &nbsp; Install CUDA (for GPU support)
The first step to configure your own TensorFlow environment is to set up CUDA and CuDNN. CUDA is a GPU computing API created by NVIDIA, which TensorFlow builds upon. TensorFlow 2 requires CUDA version 10 or above. To install CUDA, you need to first make sure that you have a [CUDA-enabled GPU card](https://developer.nvidia.com/cuda-gpus). If you don't have a CUDA GPU, then you can skip this section and move to the next section---in this case, however, you will be limited to run TensorFlow on CPU  (no GPU acceleration). If you do have a CUDA GPU, first go ahead and [install/update your graphics card driver](https://www.nvidia.com/download/index.aspx?lang=en-us). For the actual installation of CUDA and CuDNN, see the instructions below per different operating systems.

### On Windows
First, [download CUDA toolkit](https://developer.nvidia.com/cuda-toolkit-archive). Make sure that you download the [right version compatible with TensorFlow](https://www.tensorflow.org/install/source_windows#gpu). For TensorFlow 2.4.1 (newest version as of Jan. 27, 2021), you need to install CUDA 11.0. Do not just download the newest version. Once you are done with downloading CUDA, go ahead and install it by running the `*.exe` file you just downloaded. Mostly you can click "next" in the installation wizard all the way through the end.

After CUDA is installed, [download CuDNN](https://developer.nvidia.com/rdp/cudnn-archive), a CUDA add-on for deep neural networks (DNN). Again, make sure you download CuDNN version that's [compatible with your TensorFlow version](https://www.tensorflow.org/install/source_windows#gpu). Do not just download the newest version. For downloading CuDNN, you will need to sign up as an NVIDIA developer. After downloading it, install CuDNN by copying and pasting the contents of the downloaded zip file into the corresponding folder under `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\<cuda-version>`.

### On Linux
TODO: Place an instruction here.

### On Mac
TODO: Place an instruction here.


## 2.3. &nbsp; Install TensorFlow
Once you have CUDA and CuDNN set up, installing TensorFlow itself is pretty easy. First, open a terminal/command prompt and create a [virtual environment](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) using conda:
```bash
conda create -n dlcourse python=3.8 ipykernel nb_conda_kernels
```
This is a command to create a virtual environment with the name `dlcourse` and initialize it with Python version 3.8, alongside `ipykernel` and `nb_conda_kernels` packages. The virtual environment can be activated by typing the following command:
```bash
conda activate dlcourse
```
Once you have the virtual environment activated, type the command below to install TensorFlow:
```bash
pip install tensorflow
```
To verify TensorFlow installation, see if you can run the following command without an error:
```bash
python -c "import tensorflow; tensorflow.config.list_physical_devices('GPU')"
```
If you see a bunch of messages saying "Successfully opened dynamic library XXXXX.dll", as well as the name of your GPU card (in case you have a CUDA-enabled GPU card), you are now ready to play with TensorFlow.

## 2.4. &nbsp; Clone this repository
Open a terminal/command prompt and get in to the folder you would like to have the course materials. If you are new to the command line interface, take time to study [this (for Windows)](https://www.digitalcitizen.life/command-prompt-how-use-basic-commands/) or [this (for Linux/Mac)](https://www.earthdatascience.org/courses/intro-to-earth-data-science/open-reproducible-science/bash/bash-commands-to-manage-directories-files/). Once you are in the folder, go ahead and type the following command to make a copy of this repository.

```bash
git clone https://github.com/stephenbaek/dlcourse.git
```
If you are a Windows user, you will need to [install git](https://git-scm.com/download/win) before to run the command above.

After the course materials are cloned, get into the course directory by typing the following command:
```bash
cd dlcourse
```

Then, run the following command to install all the required dependencies. Make sure that you activate the conda virtual environment (see above), before to run this command.
```bash
pip install -r requirements.txt
```
## 2.5. &nbsp; Run the course materials
Congratulations! You are now ready to run the course materials on your local machine. To view the materials, simply run the following command:
```bash
jupyter notebook
```

