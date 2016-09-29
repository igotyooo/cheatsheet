Add the following to `~/.bashrc` in the host.
```
# added by me.
cd ~/
alias v='vim'
```
Add the following to `~/.bashrc` inside image.
```
# added by me.
alias v='vim'
alias docker='sudo nvidia-docker'
alias torchos='sudo nvidia-docker run -it -u dgyoo \
                -v ~/workspace/:/home/dgyoo/workspace/ \
                -v ~/workspace/src:/home/dgyoo/workspace/src \
                -v /data1/dgyoo/datain/:/home/dgyoo/workspace/datain \
                -v /data2/dgyoo/dataout:/home/dgyoo/workspace/dataout \
                dgyoo/cuda-torch:latest'
alias torchosroot='sudo nvidia-docker run -it -u root dgyoo/cuda-torch:latest'
. /root/torch/install/bin/torch-activate
```
