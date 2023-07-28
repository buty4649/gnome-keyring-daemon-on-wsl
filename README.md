# gnome-keyring-daemon-on-wsl

## Usage

setup systemd/User

```sh
mkdir ~/.config/systemd/user
wget -P ~/.config/systemd/user https://raw.githubusercontent.com/buty4649/gnome-keyring-daemon-on-wsl/main/gnome-keyring-daemon.service
wget -P ~/.config/systemd/user https://raw.githubusercontent.com/buty4649/gnome-keyring-daemon-on-wsl/main/gnome-keyring-daemon.socket
wget -P ~/.config/systemd/user https://raw.githubusercontent.com/buty4649/gnome-keyring-daemon-on-wsl/main/start-gnome-keyring-daemon
chmod +x ~/.config/systemd/user/start-gnome-keyring-daemon

systemctl --user daemon-reload
systemctl --user enable --now gnome-keyring-daemon.service
```

for bash

```sh
echo "export SSH_AUTH_SOCK=/run/user/1000/keyring/ssh" >> ~/.bashrc
```

for fish-shell

```sh
echo "set -x SSH_AUTH_SOCK /run/user/1000/keyring/ssh" >> ~/.config/fish/config.fish
```
