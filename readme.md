# Post Ubuntu Fresh Install

```shell
sudo apt update && sudo apt upgrade -y
```

### Installing `zsh`

- `sudo apt install zsh`
- `chsh -s $(which zsh)`
- reload terminal/ssh

---

### Shell Customization

- install [`oh-my-zsh`](https://github.com/ohmyzsh/ohmyzsh?tab=readme-ov-file#basic-installation)
- install [`p10k`](https://github.com/romkatv/powerlevel10k?tab=readme-ov-file#oh-my-zsh) for omz
- install [`zsh-syntax-highlighting`](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md#oh-my-zsh)
  for omz
- `cp ./zsh/.p10k.zsh ./zsh/.zshrc .`
- reload terminal/ssh

---

### Configuring `git`

- `git config --global user.name "Sebastien Green"`
- `git config --global user.email "sebygreen@gmail.com"`

> WSL2
>
> - install Git for Windows with GCM
> - `git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/bin/git-credential-manager.exe"`

---

### Installing Node via [`nvm`](https://github.com/nvm-sh/nvm?tab=readme-ov-file#installing-and-updating)

- `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.0/install.sh | bash`
- `nvm i --lts`
- `npm i -g npm npm-check-updates prettier`

> Updating
>
> - `nvm i --lts --reinstall-packages-from={previous}`

##### PM2

- `npm install pm2 -g`
- `pm2 startup`

> Executing a Node command
>
> - `pm2 start npm --name {name} -- {command}`

---

### Installing `php`

- `sudo apt install php`

| 20.04 LTS | 22.04 LTS | 24.04 LTS |
| --------- | --------- | --------- |
| 7.4       | 8.1       | 8.3       |

> If a specific `php` version is required
>
> - `sudo add-apt-repository ppa:ondrej/php`
> - `sudo apt update`
> - `sudo apt install php{version}`

##### Composer

- `sudo apt install php-cli unzip`
- `cd ~ && curl -sS https://getcomposer.org/installer -o /tmp/composer-setup.php`
- `sudo php /tmp/composer-setup.php --install-dir=/usr/local/bin --filename=composer`

---

### Installing Docker

- `sudo apt update`
- `sudo apt install ca-certificates curl`
- `sudo install -m 0755 -d /etc/apt/keyrings`
- `sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc`
- `sudo chmod a+r /etc/apt/keyrings/docker.asc`

```shell
echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
$(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

- `sudo apt update`
- `sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin`
