---
layout: default
title: "Pt.1 Serveis D'inici"
permalink: projecte2/sprint1/
---

## jjjj

Serveis d'inici

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
