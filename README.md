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
```
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
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

# install zsh-autosuggestions zsh-syntax-highlighting plugins
git clone https://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting $ZSH_CUSTOM/plugins/zsh-syntax-highlighting

# modify the config file of oh-my-zsh
vim ~/.zshrc

## change zsh style
ZSH_THEME="candy"

## add plugins
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)

# activate changes
source ~/.zshrc
```
