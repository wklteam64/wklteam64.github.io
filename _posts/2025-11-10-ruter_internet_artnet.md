---
# category: page
layout: post
title: Czy Ruter i Artnet wymagają dostępu do Internetu? 
author: WKL TEAM64
# sidebar_link: true
---

<!-- # Czy Ruter i Artnet wymagają dostępu do Internetu?  -->

 **Czy Ruter i Artnet wymagają dostępu do Internetu?**  

Czesto pojawia się pytanie czy do prawidłowego działania sieci Artnet i sterowania oświetleniem potrzebny jest dostęp do Internetu. Szczególnie gdy w zestawie znajduje się ruter.

> **Dobra wiadomość jest taka, że Internet nie jest potrzebny.**

Ruter jest urządzeniem samodzielnym, które nie potrzebuje zakupu internetu do prawidłowego funkcjonowania, on po prostu tworzy własną sieć LAN dostępną poprzez Wi-Fi lub gniazda Ethernet. 

**Tak więc w przypadku sieci Artnet, ruter pełni rolę centrum komunikacyjnego, umożliwiając przesyłanie danych DMX pomiędzy kontrolerem a urządzeniami oświetleniowymi bez konieczności korzystania Internetu.**

To urządzenie posiada złącza RJ-45 LAN(od ang. Local Area Network) i WAN(od ang. wide area network). 


![gniazda LAN WAN rutera tplink](https://wklteam64.github.io/img/inGniazdaTplink.webp)
***Rysunek nr 1: Gniazda RJ-45 rutera TPLINK, kolorem żółtym oznaczone są gniazda LAN, a niebieskim WAN***

![gniazda LAN WAN rutera dlink](https://wklteam64.github.io/img/in_gniazda_dlink.webp)
***Rysunek nr 2: Gniazda RJ-45 rutera DLINK, kolorem szarym oznaczone są gniazda LAN, a żółtym WAN***

> *Na podstawie rysunków nr 1 i 2 gniazda LAN i WAN posiadają różną kolorystykę, ale gniazdo LAN i WAN różni się od siebie w danym modelu innym kolorem i dodatkowo są od siebie rozdzielone. Istnieją modele które złącze jest w formacie RJ-11(DSL, ADSL) lub brak gdy posiadają modem z dostępem do sieci komórkowej*

>  **Podsumowując:** *gniazda LAN służą do podłączania urządzeń w sieci lokalnej (np. komputery, drukarki, kontrolery DMX, bramki Artnet itp.), natomiast gniazdo WAN jest używane do podłączenia rutera do zewnętrznej sieci, takiej jak Internet.*

![gniazda LAN WAN rutera dlink](https://wklteam64.github.io/img/inRutWifi01.webp)
***Rysunek nr 3: Typowy schemat pracy ruterów domowych z podłączeniem do internetu poprzez złącze WAN lub coś w rodzaju jako modem LTE. Dla potrzeb biura lub domu brak internetu byłby niepożądany z oczywistych względów, zaś dla innych zastosowań nie jest obowiązkowy i można go pominąć***

Część WAN i LAN może być w ruterze fizycznie rozdzielona lub występować jako jedno złącze konfigurowalne programowo. Gdy są rozdzielone od siebie to złącze WAN ma oddzielną konfigurację.

![gniazda LAN WAN rutera dlink](https://wklteam64.github.io/img/inWanSet.webp)
***Rysunek nr 4: Przykład konfiguracji złącza WAN opisanego w tym modelu jako Internet***


Ruter może być skonfigurowany jako serwer DHCP, który będzie przydzielał adresy IP podłączonym urządzeniom lub urządzenia mogą mieć ustawione statyczne adresy IP w tej samej podsieci