# Post fresh install
1. install [nvm](https://github.com/nvm-sh/nvm?tab=readme-ov-file#installing-and-updating)
   1. `nvm i --lts`
   2. `npm i -g npm npm-check-updates prettier`
   3. to update `nvm i --lts --reinstall-packages-from={previous}`
2. configure git
   1. `git config --global user.name "Sebastien Green"`
   2. `git config --global user.email "sebygreen@gmail.com"`
   3. if WSL2
      1. install Git for Windows with GCM
      2. `git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/bin/git-credential-manager.exe"`
3. configure shell
   1. `sudo apt install zsh`
   2. `chsh -s $(which zsh)`
   3. reload terminal
4. install [oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh?tab=readme-ov-file#basic-installation)
5. install [p10k](https://github.com/romkatv/powerlevel10k?tab=readme-ov-file#oh-my-zsh) for omz
6. install [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md#oh-my-zsh) for omz
7. `cp ./zsh/.p10k.zsh ./zsh/.zshrc .`
8. reload terminal
