# How to Install TensorFlow 2.5.0 on the M1 Mac

1. Install Homebrew:
    ```
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```
2. Install Xcode build tools:
    ```
    xcode-select --install
    ```
3. Download and install Miniforge from the following URL:
    - https://github.com/conda-forge/miniforge
    - Download the ARM64 version
4. Create a new virtual environment and activate it:
    ```
    conda create --name env_tensorflow python=3.9
    conda activate env_tensorflow
    ```
5. Install TensorFlow:
    ```
    conda install -c apple tensorflow-deps
    pip install tensorflow-macos  # it should fail
    pip install tensorflow-metal
    pip install tensorflow-macos --no-dependencies
    pip install flatbuffers --no-dependencies
    ```
6. Verify the installation was successful:
    ```
    python
    
    >>> import tensorflow as tf
    >>> tf.__version__
    2.5.0
    ```