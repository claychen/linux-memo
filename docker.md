# docker

- install
  - ref  https://docs.docker.com/install/linux/docker-ce/ubuntu/#docker-ee-customers
  - special issue aboue docker-ce on ubuntu 18.04
    - https://github.com/docker/for-linux/issues/290
- `docker-compose`
  - install ref https://docs.docker.com/compose/install/#install-compose
  -  



# apt

- `apt-cache policy`
  - show the repository information
- `grep ^deb /etc/apt/sources.list`
- `apt-add-repository`
  - sudo add-apt-repository "deb http://download.virtualbox.org/virtualbox/debian `lsb_release -cs` contrib"
    - add repository to /etc/apt/sources.list
  - `apt-add-repository remove repo-name`
    - remove the repo 
- apt-cache policy package-name` 
  - show the installation details of specified package
- `apt list installed`
  - show installed packages
  	 ​		 

# typora

- installation

  - ref https://support.typora.io/Typora-on-Linux/

```shell
    # optional, but recommended
    sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys BA300B7755AFCFAE
    
    # add Typora's repository
    sudo add-apt-repository 'deb https://typora.io/linux ./'
    sudo apt-get update
    
    # install typora
    sudo apt-get install typora
```

# tmux

- ref https://larrylu.blog/tmux-33a24e595fbc
- page 
  - c-b % : create a horizontal pane
  - c-b " : create a vertical pane
  - c-b direction : move to another pane
  - c-b x : close
- window
  - c-b c : create new window
  - c-b & : close current window
  - c-b p : go to previous window
  - c-b n : go to next window
- session
  - tmux : create a new session
  - tmux ls : list sessions
  - tmux attach -t 0 : attach session 0
  - tmux kill-session -t 0 : close session 0
  - c-b d : dettach from session
  - c-b s : go to next session

# DNS
- `127.0.0.53` when i am using wifi, i found dns was confiqured as `127.0.0.53` in `/etc/resolv.conf` by `systemd-resolved`

- Disable systemd-resolved and reboot. nameserver 127.0.0.53 is not written to /etc/resolv.conf. 

  - command

    ```
    $ sudo systemctl disable systemd-resolved
    $ sudo reboot
    ```

- ref : https://www.hiroom2.com/2017/08/24/ubuntu-1610-nameserver-127-0-0-53-en/



# Setting PPPoE with nmcli

- Using nmcli in ubuntu 18.04

```shell
sudo nmcli con edit type pppoe con-name DSL-NAME
# going to the interactive mode in nmcli
nmcli> set pppoe.username DSL-ACCOUNT
nmcli> save
nmcli> quit
# go to UI to set password	
```

- If wired connection are showed as 'unmanged'

```shell
sudo vim /etc/NetworkManager/NetworkManager.conf
# modify ifupdown setction
managed=true
```

- Reference

  - https://askubuntu.com/questions/882806/ethernet-device-not-managed

    