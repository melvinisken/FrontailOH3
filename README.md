# FrontailOH3
Frontail installation for OpenHAB 3 on Debian 10

Prerequisites

(coming from a clean Debian 10 minimal image, installed OpenHAB, Influx and Grafana so far)

install nodejs

 apt install curl
 
 curl -sL https://deb.nodesource.com/setup_15.x | bash -
 
 apt install -y nodejs
 
install frontail

 npm i frontail -g
 
the following folders are used:

frontail installation folder: echo "$(npm list -g | head -n 1)/node_modules/frontail"

(for me /usr/lib/node_modules/frontail/ )

copy frontail-preset.json to /usr/lib/node_modules/frontail/preset/openhab.json

copy frontail-theme.css to /usr/lib/node_modules/frontail/web/assets/styles/openhab.css

copy frontail.service to /etc/systemd/system/frontail.service

Reload: systemctl daemon-reload 

Start: systemctl enable --now frontail.service 

Check if it'S running: systemctl status frontail.service 
