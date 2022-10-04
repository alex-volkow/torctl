## Description

Script to redirect all traffic through tor network including dns queries
for anonymizing entire system

## Installation

`pacman -S torctl`

## Installation - Debian

`sudo apt install tor`
`sudo apt install git`

Install GNU MAC changer. GNU MAC changer allows you to change your MAC address.
`sudo apt install tor macchanger secure-delete`

Clone the Torctl directory:
`git clone https://github.com/alex-volkow/torctl && cd torctl`

Move the contents of the "service" and "completion" folders. If you are using a regular Linux distribution, there are a few files you need to move. 
`sudo mv service/* /etc/systemd/system/`
`sudo mv bash-completion/torctl /usr/share/bash-completion/completions/torctl`

Edit the input commands of the script. If you are using a regular Linux distribution, you need to edit the input commands of the script. Skip this step if you are using BlackArch.
`sed -i 's/start_service iptables//' torctl`
`sed -i 's/TOR_UID="tor"/TOR_UID="debian-tor"/' torctl`

Move the Torctl script you just edited. After you finish editing the script, go ahead and enter the following command:
`sudo mv torctl /usr/local/bin/torctl`

Remove the Torctl script from the original folder.
`cd .. && rm -rf torctl/`

## Usage

```
$ torctl
--==[ torctl.sh by blackarch.org ]==--

Usage: torctl.sh COMMAND

A script to redirect all traffic through tor network

Commands:
  start      - start tor and redirect all traffic through tor
  stop       - stop tor and redirect all traffic through clearnet
  status     - get tor service status
  restart    - restart tor and traffic rules
  autowipe   - enable memory wipe at shutdown
  autostart  - start torctl at startup
  ip         - get remote ip address
  chngid     - change tor identity
  chngmac    - change mac addresses of all interfaces
  rvmac      - revert mac addresses of all interfaces
  version    - print version of torctl and exit

```

## Get Involved

You can get in touch with the BlackArch Linux team. Just check out the following:

**Please, send us pull requests!**

**Web:** https://www.blackarch.org/

**Mail:** team@blackarch.org

**IRC:** [irc://irc.freenode.net/blackarch](irc://irc.freenode.net/blackarch)
