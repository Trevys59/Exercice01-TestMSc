# Exercice01-TestMSc
Création d’un « miniLab » sur Packet Tracer

## Topologie
- 1x Cisco 1941 (g0/0 trunk LAN, g0/1 vers ISP)
- 3x Switch PT (ports 1 & 9 trunk)
- 3x AP PT-AC (VLAN 20)
- 3x Laptops (Wi-Fi VLAN 20), 6x PC fixes (VLAN 20), 3x Téléphones IP (VLAN 1), 3x PC admin (VLAN 30)

## VLANs & Adressage
- VLAN 1 (VoIP): 192.168.0.0/24 (GW .1, DHCP .10–.50)
- VLAN 10 (PC fixes): 192.168.10.0/24 (GW .1, DHCP .10–.50) *réservé si besoin futur*
- VLAN 20 (Wi-Fi & PC fixes): 192.168.20.0/24 (GW .1, DHCP .10–.50)
- VLAN 30 (Admin): 192.168.30.0/24 (GW .1, DHCP .10–.50)

> Note: Incohérence corrigée (AP en VLAN 20 car VLAN 20 = Wi-Fi dans l’adressage).

## Étapes
1. Trunks sur ports 1 & 9 des switches
2. Affectation des ports d’accès (VoIP=VLAN1, Wi-Fi/PC fixes=VLAN20, Admin=VLAN30)
3. Router-on-a-stick (g0/0.1 native, .10, .20, .30) + DHCP pools
5. AP en VLAN 20 (DHCP), SSID WPA2
6. Route par défaut vers ISP, tests
