### Hi there 👋

- 🔭 I’m currently a Ph.D. candidate in the Chinese University of Hong Kong, Shenzhen.
- 🌱 I’m currently learning 3D vision in microcosm.
- 👯 I’m looking to collaborate on 3D vision in microcosm.
- 🤔 I’m looking for help me make the world easier.
- 💬 Ask me about coding, papers or anything interesting!
- 📫 How to reach me: https://simonhanyang.github.io/
- 😄 Pronouns: Panda
- ⚡ Fun fact: Computer Vision Researcher but Still LOVE CODING APPs AND ANYTHING INTERESTING! 

## AI Station Server

- Using tensorboard on remote server `ssh -L 16006:127.0.0.1:6006 cuhk`
- Saving remote server's ip and port into the local computer `~/.ssh/config` by the following format:
```bash
Host cuhk
    User root
    HostName 10.xx.xxx.16
    Port xxxxx
```
- Do not use pwd to log in to the remote server: saving local computer's `~/.ssh/id_rsa.pub` to remote `~/.ssh/authorized_keys`
- Using `Oh-my-ZSH` on remote server:
```bash
# update apt or apt-get
apt update/upgrade
apt-get update/upgrade

# install zsh
apt install zsh

# check SHELL
echo $SHELL

# switch to zsh
chsh -s /bin/zsh

# install oh-my-zsh
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)" -y
## oh-my-zsh in China
sh -c "$(curl -fsSL https://gitee.com/shmhlsy/oh-my-zsh-install.sh/raw/master/install.sh)"
## in China
sh -c "$(wget -O- https://install.ohmyz.sh/)"

# install zsh-autosuggestions zsh-syntax-highlighting plugins
git clone https://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
# in China
git clone https://gitee.com/hailin_cool/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
git clone https://gitee.com/Annihilater/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting

# modify the config file of oh-my-zsh
vim ~/.zshrc

## change zsh style
ZSH_THEME="candy"

## add plugins
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)

# activate changes
source ~/.zshrc
```
- Using anaconda3 on an individual account on an AI Station (Do not have sudo permission)
```bash
# download anaconda3
wget https://mirrors.bfsu.edu.cn/anaconda/archive/Anaconda3-2023.09-0-Linux-x86_64.sh --no-check-certificate

# install anaconda3
bash Anaconda3-2021.11-Linux-x86_64.sh

## when installing, pls change the config file root to anaconda3
### original
/root/anaconda3/bin
### change to the individual account
/uname/anaconda3/bin

# change environment variable for anaconda3
vim /etc/profile

## add the following command to the end of `/etc/profile`
export PATH=/uname/anaconda3/bin:$PATH

# activate changes
source /etc/profile

# init conda, if using zsh and need to open a new bash
conda init zsh
```

### Download 12.8 CUDA-toolkit[nvcc -V] on CUHKsz servers
```
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/cuda-ubuntu2004.pin
mv cuda-ubuntu2004.pin /etc/apt/preferences.d/cuda-repository-pin-600
wget https://developer.download.nvidia.com/compute/cuda/12.8.0/local_installers/cuda-repo-ubuntu2004-12-8-local_12.8.0-570.86.10-1_amd64.deb
dpkg -i cuda-repo-ubuntu2004-12-8-local_12.8.0-570.86.10-1_amd64.deb
cp /var/cuda-repo-ubuntu2004-12-8-local/cuda-*-keyring.gpg /usr/share/keyrings/
apt-get update
apt-get -y install cuda-toolkit-12-8

# officially
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/cuda-ubuntu2004.pin
sudo mv cuda-ubuntu2004.pin /etc/apt/preferences.d/cuda-repository-pin-600
wget https://developer.download.nvidia.com/compute/cuda/12.8.0/local_installers/cuda-repo-ubuntu2004-12-8-local_12.8.0-570.86.10-1_amd64.deb
sudo dpkg -i cuda-repo-ubuntu2004-12-8-local_12.8.0-570.86.10-1_amd64.deb
sudo cp /var/cuda-repo-ubuntu2004-12-8-local/cuda-*-keyring.gpg /usr/share/keyrings/
sudo apt-get update
sudo apt-get -y install cuda-toolkit-12-8
```


### Tips/Bugs
- For Linux: `ImportError: libGL.so.1: cannot open shared object file: No such file or directory`
```bash
apt install libgl1-mesa-glx
```
- CUDA out of Memory
```
fuser -v /dev/nvidia*
kill -9 pid
```
![image](https://github.com/SimonHanYANG/SimonHanYANG/assets/124108306/9bc67550-c595-4981-aba0-52d309fe6368)

