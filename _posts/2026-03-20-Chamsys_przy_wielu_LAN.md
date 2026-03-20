---
layout: post
title: Konfiguracja wielu kart sieciowych LAN na jednym komputerze na przykładzie CHAMSYS MAGICQ, FREESTYLER, QLC+
author: WKL TEAM64
---

## Wprowadzenie

Protokół **ArtNet** ma dwie natywne adresacje IPv4:
* **PRIMARY** od 2.0.0.1 do 2.255.255.255 z maską 255.0.0.0  
* **SECONDARY** od 10.0.0.1 do 10.255.255.255 z maską 255.0.0.0

Co oznaczałoby obligatoryjne stosowanie się do zaleceń dokumentacji. Ale bywają odstępstwa podyktowane m.in : narzuconymi regulacjami działów IT, ograniczeniami urządzeń sieciowych jak rutery.

Wtedy można używać adresacji ip v4 np: 192.168.1.0/24 (inaczej maska 255.255.255.0) znanymi w domowych lub firmowych sieciach. 

> Aplikacje DMX512 takie jak Grandma 2, 3, dot2 ONPC wymaga bezwględnie adresacji **PRIMARY** lub **SECONDARY**

Inne pozwalają na stosowanie dowolnej, ale np: **CHAMSYS MAGICQ** przy podłączaniu bramek artnet do swoich konsol wymaga już stosowania adresacji narzuconej przez **ARTNET**. 

## Więcej niż jedna karta sieciowa 

Jeżeli w systemie posiadamy jedną kartę sieciową i ustawimy ją na adresację 192.168.1.x/24 aby nie zmieniać fabrycznych ustawień bramki ARTNET "PROMYK 3.60" wtedy połączenie z bramką funkcjonuje prawidłowo 

![modul radiowy](https://wklteam64.github.io/img/stCHM.webp)

Do czasu gdy dołożymy ruter (coraz częstsze zdarzenie) z adresacją 192.168.1.x/24 co spowoduje w CHAMSYS MAGICQ błąd konfiguracji. 

**Należy wtedy postępować według punktu pierwszego lub drugiego:**

1. **zmiana adresu LAN rutera** z ***192.168.1.1*** na np: **192.168.2.1**. Byle drugi trzeci oktet był różny od x.x.1.x np 192.168.0.1 , 192.168.200.1 itp a nie inny adres z sieci 192.168.1.1

2. **zmiana adresu Promyka 3.60** na adres **2.168.1.30 /8** oraz zmiana adresu karty sieciowej LAN komputera na **2.0.0.1 /8**. Ta procedura jest opisana w instrukcji PROMYK 3.60, instrukcjach i filmie do których linki są tej stronie statycznej dokumentacji. 

> Częstym błędeem jest wpisywanie tego samego adresu ip v4 bramki artnet do ustawień  karty LAN komputera.
---
Wydaje się że zmiana adresu IPv4 **2.x.x.x/8** od razu zapobiega takim zdarzeniom konfliktu dwóch sieci LAN o tej samej adresacji. Tak do końca nie jest. Są przypadki gdy jedna karta LAN ma już adres ipv4 2.0.0.1/8 a druga jeszcze nie ma żadnego, a użytkownik ma zamiar użyć drugiej bramki artnet bez np: switch'a. Wtedy ustawia np: 2.0.0.2/8 i okazuje się że wszystko przestaje działać. Wtedy powinien ustawić tą LAN nr 2 na adres np: **10.0.0.1/8** i zmienić adres Promyk 3.60 na np: **10.168.1.30/8**.

---


## Instrukcje wspomniane w artykule 

* https://wklteam64.github.io/2026/01/02/uruchomienie-artnet-w-30-sekund.html
* https://wklteam64.github.io/category/edge-case.html video poradniki
* https://wklteam64.github.io/manual.html instrukcje PDF do bramek ARTNET PROMYK 2.00 i 3.xx
* https://wklteam64.github.io/2025/11/10/ruter_internet_artnet.html

