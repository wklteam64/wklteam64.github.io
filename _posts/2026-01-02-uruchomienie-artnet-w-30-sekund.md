---
layout: post
title: Uruchomienie bramki Artnet PROMYK 3.60 w 30 sekund w systemach Windows, macOS i Linux
author: WKL TEAM64
---

***Uruchomienie bramki Artnet PROMYK 3.60 w 30 sekund w systemach Windows, macOS i Linux***

Bramka Artnet PROMYK 3.60 jest urządzeniem sieciowym, które umożliwia przesyłanie sygnałów DMX przez protokół Artnet w sieciach Ethernet. Poniżej przedstawiamy szybki sposób na uruchomienie tej bramki w zaledwie 30 sekund.

Taki czas wymaga jedynie podłączenia bramki do zasilania oraz ustawienia adresu IP karty sieciowej komputera w systemach Windows, macOS lub Linux

**1. Przypadek konfiguracji w podsieci 192.168.1.x dla komputera z kartą sieciową LAN bez innych kart sieciowych jak np:Wi-Fi**

Bramka PROMYK 3.60 ma domyślny adres IP: **192.168.1.30 z maską podsieci 255.255.0.0**
co oznacza, że karta sieciowa komputera/konsoli powinna mieć adres IP z tej samej podsieci, np. **192.168.1.2** z maską podsieci **255.255.255.0**

> **UWAGA:** W kartach sieciowych LAN nie ma włączonego protokołu DHCP, więc adres IP musi być ustawiony ręcznie i adresy IP muszą być inne niż adres bramki PROMYK 3.60. **Częstym błędem jest ustawienie adresu IP karty sieciowej na ten sam adres co bramka PROMYK 3.60**

> **UWAGA:** Jeżeli komputer ma więcej niż jedną kartę sieciową (np. Wi-Fi i LAN) to należy wyłączyć kartę sieciową Wi-Fi lub ustawić jej adres IP w innej podsieci niż 192.168.1.x, np. 192.168.0.x lub 10.0.0.x 

W systemie Windows należy wejść w ustawienia karty sieciowej LAN i ustawić adres IP ręcznie na jak na zdjęciu poniżej:
![ipconfig okno ](https://wklteam64.github.io/img/konfWlascIpv4a192168130.webp)
**Rysunek nr 1:Aby dostać się do tego okna ustawień należy odszukać ustawienia karty sieciowej i kliknąć w niej prawym przyciskiem myszy, a następnie wybrać opcję "Właściwości",protokół internetowy IPv4, brama domyśla zostaje pusta i ustawienia DNS**

Paremetry zatwierdzamy przyciskiem OK. Możemy teraz sprawdzić połączenie z bramką PROMYK 3.60 za pomocą polecenia ping w wierszu poleceń (cmd):

 ``` shell
  ping 192.168.1.30
  
PING 192.168.1.30 (192.168.1.30) 56(84) bytes of data.
64 bytes from 192.168.1.30: icmp_seq=1 ttl=128 time=0.157 ms
64 bytes from 192.168.1.30: icmp_seq=2 ttl=128 time=0.144 ms
64 bytes from 192.168.1.30: icmp_seq=3 ttl=128 time=0.173 ms
64 bytes from 192.168.1.30: icmp_seq=4 ttl=128 time=0.140 ms

--- 192.168.1.30 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3058ms
rtt min/avg/max/mdev = 0.140/0.153/0.173/0.012 ms


```

Jeżeli polecenie ping zakończy się sukcesem, oznacza to, że bramka PROMYK 3.60 jest poprawnie podłączona do sieci i gotowa do konfiguracji w oprogramowaniu obsługującym protokół Artnet, np. ONYX OBSIDIAN, freestyler x2, QLC+ itp.

>polecenie **ping** jest najprostszym sposobem na sprawdzenie połączenia sieciowego między komputerem a dowolnym urządzeniem sieciowym, w tym przypadku bramką PROMYK 3.60.

Drugim sposobem na sprawdzenie połączenia jest otwarcie strony konfiguracyjnej bramki PROMYK 3.60 w przeglądarce internetowej pod adresem **192.168.1.30**, co potwierdzi, że bramka jest dostępna w sieci a także umożliwi podgląd jej ustawień konfiguracyjnych oraz zmianę tych ustawień w razie potrzeby.
![web-config](https://wklteam64.github.io/img/36konfFabric192168130.webp)
