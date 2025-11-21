---
# category: page
layout: post
title: Podłączenie bramki Artnet PROMYK 3.xx do konsol TITAN AVOLITES
author: WKL TEAM64
# sidebar_link: true
---

Podłączenie bramki Artnet **PROMYK 3.xx** do konsol oświetleniowych **TITAN AVOLITES** jest bardzo proste i wymaga jedynie odpowiedniego skonfigurowania adresów IP na obu urządzeniach oraz podłączenia ich do złącza sieciowego (LAN) z tyłu konsoli.

## Konfiguracja adresów IP 

Fabrycznie bramka PROMYK 3.xx posiada ustawiony adres IP: **192.168.1.30** z maską podsieci 255.255.255.0, natomiast konsola TITAN AVOLITES może mieć różne domyślne ustawienia w zależności od modelu i wersji oprogramowania. W celu zapewnienia prawidłowej komunikacji między urządzeniami, należy ustawić adres IP konsoli w tej samej podsieci co bramka PROMYK. Na przykład, jeśli bramka ma adres ten sam co powyżej, można ustawić adres IP konsoli na **192.168.1.2** z maską podsieci 255..255.255.0.
W instrukcji obsługi konsoli TITAN AVOLITES znajduje się zalecenie aby urządzenia Art-net miały adresy IP natywne dla tego protokołu czyli zaczynające się od 2.x.x.x. W takim przypadku można ustawić adres IP bramki PROMYK na **2.168.1.30** z maską podsieci 255.0.0.0, a adres IP konsoli na **2.0.0.2** z maską podsieci 255.0.0.0.

> Uwaga: Ważne jest, aby oba urządzenia miały unikalne adresy IP w tej samej podsieci, aby uniknąć konfliktów adresów.

Sposoby jak zmienić adresy IP bramki PROMYK 3.xx zostały opisane w [tym artykule](https://wklteam64.github.io/category/edge-case.html)