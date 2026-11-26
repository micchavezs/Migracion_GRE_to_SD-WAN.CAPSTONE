# Plan de direccionamiento — Los Andes Logistics

> Generado desde `plan-direccionamiento.xlsx` (fuente de verdad). Si cambias el Excel, actualiza también este archivo.

## Sedes

| SEDE | FUNCIÓN | TRABAJADORES | BLOQUE IP | GATEWAY | WAN 1 | WAN 2 |
|---|---|---|---|---|---|---|
| CD Los Andes | Centro de distribución y coordinación con el paso fronterizo | 20 | 10.0.0.0/16 | UniFi Dream Machine Pro | VTR | STARLINK |
| CM Santiago | Administración: gerencia, finanzas y servidores; CD | 40 | 10.20.0.0/16 | UniFi Dream Machine Pro | MOVISTAR | STARLINK |
| CD Rancagua | Centro de distribución principal | 30 | 10.10.0.0/16 | UniFi Dream Machine Pro | MOVISTAR | STARLINK |
| **Total** |  | **90** |  |  |  |  |

## Plan de VLAN por sede

| Sede | VLAN ID | Nombre | Red | Gateway | DHCP inicio | DHCP fin | Política |
|---|---|---|---|---|---|---|---|
| CD Los Andes | 1 | Gestión | 10.0.0.0/24 | 10.0.0.1 | .50 | .252 | Acceso solo desde redes corporativas |
| CD Los Andes | 20 | Usuarios | 10.0.20.0/24 | 10.0.20.1 | .50 | .252 | Redes de usuarios |
| CD Los Andes | 30 | Servidores | 10.0.30.0/24 | 10.0.30.1 | .50 | .252 | Compartida entre sedes por SD-WAN |
| CD Los Andes | 40 | VoIP | 10.0.40.0/24 | 10.0.40.1 | .50 | .252 | Prioridad QoS: política PRIORIDAD-VOIP en WAN1 |
| CD Los Andes | 50 | Invitados | 10.0.50.0/24 | 10.0.50.1 | .50 | .252 | Solo Internet; aislada (regla Isolated Networks) |
| CD Los Andes | 60 | CCTV | 10.0.60.0/24 | 10.0.60.1 | .50 | .252 | Acceso solo desde Servidores o Gestión |
| Casa Matriz Santiago | 1 | Gestión | 10.20.0.0/24 | 10.20.0.1 | .50 | .252 | Acceso solo desde redes corporativas |
| Casa Matriz Santiago | 20 | Usuarios | 10.20.20.0/24 | 10.20.20.1 | .50 | .252 | Redes de usuarios |
| Casa Matriz Santiago | 30 | Servidores | 10.20.30.0/24 | 10.20.30.1 | .50 | .252 | Compartida entre sedes por SD-WAN |
| Casa Matriz Santiago | 40 | VoIP | 10.20.40.0/24 | 10.20.40.1 | .50 | .252 | Prioridad QoS: política PRIORIDAD-VOIP en WAN1 |
| Casa Matriz Santiago | 50 | Invitados | 10.20.50.0/24 | 10.20.50.1 | .50 | .252 | Solo Internet; aislada (regla Isolated Networks) |
| Casa Matriz Santiago | 60 | CCTV | 10.20.60.0/24 | 10.20.60.1 | .50 | .252 | Acceso solo desde Servidores o Gestión |
| CD Rancagua | 1 | Gestión | 10.10.0.0/24 | 10.10.0.1 | .50 | .252 | Acceso solo desde redes corporativas |
| CD Rancagua | 20 | Usuarios | 10.10.20.0/24 | 10.10.20.1 | .50 | .252 | Redes de usuarios |
| CD Rancagua | 30 | Servidores | 10.10.30.0/24 | 10.10.30.1 | .50 | .252 | Compartida entre sedes por SD-WAN |
| CD Rancagua | 40 | VoIP | 10.10.40.0/24 | 10.10.40.1 | .50 | .252 | Prioridad QoS: política PRIORIDAD-VOIP en WAN1 |
| CD Rancagua | 50 | Invitados | 10.10.50.0/24 | 10.10.50.1 | .50 | .252 | Solo Internet; aislada (regla Isolated Networks) |
| CD Rancagua | 60 | CCTV | 10.10.60.0/24 | 10.10.60.1 | .50 | .252 | Acceso solo desde Servidores o Gestión |
