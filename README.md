# Install on ubuntu
# pip:
  临时使用：
    pip install -i https://pypi.tuna.tsinghua.edu.cn/simple some-package
  永久更改：
    pip install pip -U
    pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
  
# conda:
  conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
  conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
  conda config --addchannels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/
  conda config --addchannels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/
  conda config --set show_channel_urls yes
  // remove tsinghua source
  conda config --remove-key channels
  
# cuda:
  // 可以在安装cuda的同时装显卡驱动
  wget https://developer.download.nvidia.com/compute/cuda/11.4.0/local_installers/cuda_11.4.0_470.42.01_linux.run
  sudo sh cuda_11.4.0_470.42.01_linux.run
  // 配置环境变量
  export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda-11.4/lib64
  export PATH=$PATH:/usr/local/cuda-11.4/bin
  export CUDA_HOME=$CUDA_HOME:/usr/local/cuda-11.4
  source ~/.bashrc

 # 显卡驱动:
  Disable nouveau：
    sudo vim /etc/modprobe.d/blacklist.conf or sudo gedit /etc/modprobe.d/blacklist.conf
    跳到最后一行添加 blacklist nouveau
    sudo update-initramfs -u
    重启 reboot
  删除已有驱动：
    sudo /usr/bin/nvidia-uninstall
    sudo apt-get install autoremove --purge nvidia*
    sudo apt-get --purge remove nvidia*
    sudo apt autoremove
    sudo apt-get remove --purge nvidia-\*
  Ctrl+Alt+F1~F6进入文字界面
    sudo service lightdm stop
    sudo sh ./NVIDIA-Linux-x86_64-470.42.run

# openexr:
  sudo apt-get install zlib1g-dev
  sudo apt-get install libopenexr-dev
  pip install openexr

# VNC:
  安装VNCServer软件 or 命令行安装VNCServer
  安装屏幕共享xdrp
  右上角设置里设置sharing
  客户端安装Remmina，利用VNC服务器的ip地址控制
# samba:
  sudo apt-get install samba samba-common
  
