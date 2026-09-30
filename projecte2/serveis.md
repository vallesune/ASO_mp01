---
layout: default
title: "Pt.1 Serveis D'inici"
permalink: projecte2/serveis/
---

## Serveis d'Inici

Targets i services

comandes
...

man init (comada info)(veiem systemd)

init num(6) nivell exec 


/lib/systemd/systemd /etc/''/'' ( etc per modif coses inst al lib)

systemctl list-units --type=target (per filtrar targets)
'''=service (per serveis)

runlevel (per veure nivell d'exec pero no va
systemctk get-default 
ls -l /lib/sys../runlevel*.target (tmp va)

systemctl isolate rescue.target (fa un reboot)

ls -l | grep target desde el lib system 

(borrem el defaut.target y creem un link nou de defautl sobre rescue.target)(ln -s)



practica

fer target nom propi
fer depemdem
farem default
tindra un .service que cridara un script per permisos root


Targets i serveis (doc)

Creem el nostre servei propi a nivell usuari 
nano ~/.config/systemd/user/valle.service
(cont)
[Unit]
Description=Servei de captura de pantalla
After=graphical-session.target
PartOf=graphical-session.target

[Service]
Type=oneshot
RemainAfterExit=yes
ExecStart=%h/.config/valle.sh


Despres creem de la mateixa manera el nostre target a nivell user
nano ~/.config/systemd/user/valle.target
(cont)
[Unit]
Description=Target de monitoritzacio
Requires=graphical-session.target
After=graphical-session.target

Wants=valle.service

[Install]
WantedBy=default.target


Guardem el target i reiniciem el dimoni
systemctl --user daemon-reload

Podem comprovar que existeixen 
systemctl --user list-unit-files | grep valle

Iniciem el target al moment i comprovem que apareix actiu
systemctl --user start valle.target
systemctl --user status valle.target

