### Installing NVIDIA graphic driver *ONLY*
```
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo add-apt-repository ppa:graphics-drivers/ppa
$ sudo apt-get update
$ sudo apt-get install nvidia-367
$ sudo apt-get install mesa-common-dev
$ sudo apt-get install freeglut3-dev
$ sudo reboot
$ nvidia-smi
```

### Installing Cuda toolkit (if you are not use nvidia-docker)
1. Verify that your GPU is CUDA-capable.</br>
`$ lspci | grep -i nvidia`
2. Verify you have gcc installed.</br>
`$ gcc --version`
3. Download [cuda-toolkit](https://developer.nvidia.com/cuda-toolkit) installation file *.deb.
4. Depackage that.</br>
`$ sudo dpkg -i cuda-repo-<distro>_<version>_<architecture>.deb`</br>
`$ sudo apt-get update`</br>
5. If you don't have a graphic driver installed so you wanted to install that together,</br>
press `ctrl`+`alt`+`F1` and </br>
`$ sudo service lightdm stop`</br>
6. Install cuda-toolkit and reboot.</br>
`$ sudo apt-get install cuda`</br>
`$ sudo reboot`</br>
7. Download and extract [cuDNN](https://developer.nvidia.com/cudnn) in your preferred location.
8. Add the following in your `~/.bashrc`</br>
`$ export PATH=/usr/local/cuda/bin:$PATH`</br>
`$ export LD_LIBRARY_PATH=/usr/local/cuda/lib64:$LD_LIBRARY_PATH`</br>
`$ export LD_LIBRARY_PATH=<cuDNN path>:$LD_LIBRARY_PATH`</br>

**Note)** To use cuDNN, add `<cuDNN path>` to your build and link process by adding `-I <cuDNN path>` to your compile line and `-L <cuDNN path> -lcudnn` to your link line.
