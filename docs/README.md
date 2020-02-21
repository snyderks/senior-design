# User Documentation for Lift Classification Model

**Note: as there is not yet a CLI for the model (still in development due to 
research progress), the documentation is incomplete. It will be improved as 
these features are added.**

[Usage](./usage.md)  
[Interpretation](./interpretation.md)

## System Requirements

- [CUDA 3.5+ capable graphics card (most post-2015
  cards)](https://developer.nvidia.com/cuda-gpus)
    - Minimum 4 GB VRAM
    - Model trained on a NVIDIA GTX 960M
- Ubuntu or Windows (macOS not supported due to the NVIDIA drivers necessary)

## Basic Installation

Use of the model currently requires the Jupyter system with multiple other
dependencies. Therefore, **Anaconda 3.7** is recommended as the base system to
install.

### Anaconda

Install [Anaconda **3.7** from here](https://www.anaconda.com/distribution/). If
you install Python 2.7, many things can and will break.

### CUDA/cuDNN

1. Update your NVIDIA graphics card drivers using the NVIDIA control center or
by downloading from their [Driver Downloads
page](https://www.nvidia.com/download/index.aspx?lang=en-us).
2. Install the [CUDA Toolkit](https://developer.nvidia.com/cuda-downloads).
3. Install cuDNN [using the instructions for your operating system
here](https://docs.nvidia.com/deeplearning/sdk/cudnn-install/).

### GPU Keras

To install the GPU version of keras, run the following commands:

``` conda uninstall keras conda uninstall tensorflow conda install -c anaconda
keras-gpu ```

### Checkpoint

At this point, you should have all major dependencies installed.

To test your configuration, create a new Python file (`config_test.py`) in the
root directory of this repo, paste the following, and run it with `python
config_test.py`:

```python from tensorflow.python.client import device_lib
print(device_lib.list_local_devices()) 

from keras import backend as K print(K.tensorflow_backend._get_available_gpus())
```

Expect this to take a moment on the first run as it initializes the CUDA toolkit
and connection to your graphics card.

Your output should look like this:

```python [ name: "/cpu:0"device_type: "CPU", name: "/gpu:0"device_type: "GPU" ]
```

and should also list the GPU in the second section.

If you only have a CPU listed, training can still happen but will be
exponentially slower and so is not recommended.

If it is not listed, first attempt to run it again. If not, perform the
reinstallation process of keras-gpu using the same steps.

If you have another backend already installed (Theano as an example), Keras may
attempt to use it. See [here](https://keras.io/backend/) for how to change your
backend.


