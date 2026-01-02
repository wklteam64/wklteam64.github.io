---
layout: post
title: Pierwsze uruchomienie bramki Artnet PROMYK 3.60 w 30 sekund w systemach Windows, macOS i Linux
author: WKL TEAM64
---

***Pierwsze uruchomienie bramki Artnet PROMYK 3.60 w 30 sekund w systemach Windows, macOS i Linux***

Bramka Artnet PROMYK 3.60 jest urządzeniem sieciowym, które umożliwia przesyłanie sygnałów DMX przez protokół Artnet w sieciach Ethernet. Poniżej przedstawiamy szybki sposób na uruchomienie tej bramki w zaledwie 30 sekund.

>*Taki czas wymaga jedynie podłączenia bramki do zasilania oraz ustawienia adresu IP karty sieciowej komputera w systemach Windows, macOS lub Linux*. **Opisane niżej konfiguracje są jednorazowe, po zapisaniu ustawień bramka PROMYK 3.60 będzie działać poprawnie w kolejnych uruchomieniach bez potrzeby ponownej konfiguracji.**

**1. Przypadek konfiguracji w podsieci 192.168.1.x dla komputera z kartą sieciową LAN bez innych kart sieciowych jak np:Wi-Fi**

Bramka PROMYK 3.60 ma domyślny adres IP: **192.168.1.30 z maską podsieci 255.255.0.0**
co oznacza, że karta sieciowa komputera/konsoli powinna mieć adres IP z tej samej podsieci, np. **192.168.1.2** z maską podsieci **255.255.255.0**

> **UWAGA:** W kartach sieciowych LAN nie ma włączonego protokołu DHCP, więc adres IP musi być ustawiony ręcznie i adresy IP muszą być inne niż adres bramki PROMYK 3.60. **Częstym błędem jest ustawienie adresu IP karty sieciowej na ten sam adres co bramka PROMYK 3.60**

> **UWAGA:** Jeżeli komputer ma więcej niż jedną kartę sieciową (np. Wi-Fi i LAN) to należy wyłączyć kartę sieciową Wi-Fi lub ustawić jej adres IP w innej podsieci niż 192.168.1.x, np. 192.168.0.x lub 10.0.0.x 

W systemie Windows należy wejść w ustawienia karty sieciowej LAN i ustawić adres IP ręcznie na jak na zdjęciu poniżej:
![ipconfig okno ](https://wklteam64.github.io/img/konfWlascIpv4a192168130.webp)
**Rysunek nr 1:Aby dostać się do tego okna ustawień należy odszukać ustawienia karty sieciowej i kliknąć w niej prawym przyciskiem myszy, a następnie wybrać opcję "Właściwości",protokół internetowy IPv4, brama domyśla zostaje pusta i ustawienia DNS**

Paremetry zatwierdzamy przyciskiem OK. Możemy teraz sprawdzić połączenie z bramką PROMYK 3.60 za pomocą polecenia ping w wierszu poleceń (cmd):

 ``` bash
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
**Rysunek nr 2: Strona konfiguracyjna bramki PROMYK 3.60 pod adresem fabrycznym 192.168.1.30**

>**UWAGA:** Strona konfiguracji bramki PROMYK 3.60 jeżeli bramka ma adres IP inny niż fabryczny to będzie dostępna pod adresem obecnym a nie fabrycznym, czyli jeżeli bramka ma adres IP 2.168.100.100 to strona konfiguracyjna będzie dostępna pod adresem http://2.168.100.100. **Częstym błędem jest próba otwarcia strony konfiguracyjnej pod adresem który nie jest aktualnym adresem IP bramki PROMYK 3.60, a także próby szukania jej w internecie. Ta strona nie jest dostępna w internecie, tylko lokalnie w sieci LAN, bo jest wyzwalana przez protokół HTTP z pamięci Flash urządzenia firmy WKL TEAM64.**


[![Uruchomienie bramki Artnet PROMYK 3.60 w 30 sekund w systemie Windows](https://wklteam64.github.io/img/yt.webp)](https://youtu.be/9C-LrO0mqXc?si=7ek54gqX0FarIBnd)

Film instruktażowy pokazujący jak w 30 sekund uruchomić bramkę PROMYK 3.60 w podsieci 192.168.1.x w systemie Windows.

**2. Przypadek konfiguracji w podsieci 2.x.x.x dla komputera z kartą sieciową LAN z innymi kartami sieciowymi jak np:Wi-Fi**.

Jeżeli komputer ma więcej niż jedną kartę sieciową to należy się zorientować jakie adresy IP są używane przez inne karty sieciowe (np. Wi-Fi) i ustawić adres IP karty sieciowej LAN w innej podsieci niż używana przez inne karty sieciowe.

>**UWAGA:** częstym błędem jest używanie przez inne karty sieciowe (np. Wi-Fi) adresów IP z podsieci **192.168.1.x** co koliduje z domyślnym adresem bramki PROMYK 3.60. Jeżeli ruter Wi-Fi używa adresów z podsieci 192.168.1.x to najprościej należy zmienić adres IP karty sieciowej LAN na inną podsieć np. **2.x.x.x** z maską podsieci **255.0.0.0**

>**UWAGA:** Bramka PROMYK 3.60 w takim przypadku musi mieć zmieniony adres IP na inny niż fabryczny, np. **2.168.2.30** z maską podsieci **255.0.0.0**.

Ten przykład konfiguracji jest opisany w poście: [Konfiguracja bramki Artnet PROMYK 3.xx z oprogramowaniem z ONYX OBSIDIAN](https://wklteam64.github.io/2025/12/20/onyx_obsidian_promyk.html)

***Filmy Instruktażowe dla konfiguracji bramki PROMYK 3.60 w podsieci 2.x.x.x:***

 * **konfiguracja qlc+ freestyler dot2 onpc z bramką Artnet Promyk 3.60 w Windows 11 adresacja 2.x.x.x/8**.Film omawia przykład konfiguracji bramki artnet dmx512 "Promyk 3.60" w adresacji natywnej primary ARTNET czyli 2.0.0.0/8. Ten poradnik jest specjalnie stworzony dla osób początkujących, które dopiero zaczynają przygodę z DMX512 albo z bramkami artnet. szczegóły dostępne są na stronie firmowej WKL Team64. [Poradnik Wideo](https://youtu.be/GQle8IkHLAk?si=_ALpDQYVaOFbzwEn)
 * **Onyx obsidian 4.32 połączenie z bramką artnet PROMYK 3.xx adresacja natywna protokołu artnet win 11**  [Poradnik Wideo](https://www.youtube.com/watch?v=WJkzyEks0rM)
  
  **Podsumowanie:**
  * Pierwsze uruchomienie bramki Artnet PROMYK 3.60 w 30 sekund jest możliwe poprzez odpowiednie ustawienie adresu IP karty sieciowej komputera w tej samej podsieci co bramka.
  * Sprawdzenie połączenia można wykonać za pomocą polecenia ping lub otwarcia strony konfiguracyjnej bramki w przeglądarce internetowej.
  * W przypadku korzystania z wielu kart sieciowych, należy upewnić się, że adresy IP nie kolidują ze sobą.
  * Po poprawnym uruchomieniu bramki, można ją skonfigurować w oprogramowaniu obsługującym protokół Artnet.
  * Można ułatwić sobie pracę przy konfiguracji bramki PROMYK 3.60 korzystając z dostępnych poradników wideo przygotowanych przez WKL TEAM64 oraz dokumentacji dostępnej na stronie firmowej WKL TEAM64.
  * W razie problemów z konfiguracją, warto skonsultować się z dokumentacją techniczną lub skontaktować się z pomocą techniczną WKL TEAM64.
  * Dużą pomocą będzie program : https://www.lightjams.com/artnetominator/ który pozwala na śledzenie ruchu Artnet w sieci LAN, diagnozowanie problemów z komunikacją, wyświetalnie aktywnych Universe oraz wartości DMX przesyłanych do z bramki PROMYK 3.60 z aplikacji DMX512.
  * Bramka Artnet **PROMYK 3.60** nie wymaga specjalistycznej wiedzy sieciowej do uruchomienia, wystarczy podstawowa znajomość konfiguracji adresów IP.
  * Bramka Artnet **PROMYK 3.60** działa w standardowych sieciach Ethernet i nie wymaga specjalnych urządzeń sieciowych.
  * Bramka Artnet **PROMYK 3.60** jest kompatybilna z każdym oprogramowaniem obsługującym protokół Artnet, co czyni ją uniwersalnym rozwiązaniem dla różnych zastosowań scenicznych i oświetleniowych.Wyjątkiem są aplikacje które nie są darmowe i wymagają licencji komercyjnej np. Madrix, Light Rider itp.
  * Bramka Artnet **PROMYK 3.60** jest łatwa w konfiguracji i obsłudze, co pozwala na szybkie wdrożenie jej w różnych projektach oświetleniowych.
  * Bramka Artnet **PROMYK 3.60** jest niezawodna i stabilna w działaniu, co zapewnia ciągłość pracy systemów oświetleniowych opartych na protokole Artnet.
  * Protokół Artnet jest szeroko stosowany w branży oświetleniowej, co czyni bramkę PROMYK 3.60 atrakcyjnym rozwiązaniem dla profesjonalistów i amatorów. Ci drudzy mogą korzystać z darmowego oprogramowania do obsługi protokołu Artnet, tego typu jak QLC+, Freestyler, które używali wcześniej z interfejsami USB DMX512 open enttecc. Zaś osoby całkowiwcie nowe w temacie otrzymują urządzenie sterujące DMX512 z protokołem Artnet pozbawione wad interfejsów USB DMX512 które często sprawiają problemy z kompatybilnością w nowych systemach operacyjnych (znikanie sterowników, czasowe lub całkowite nieprawidłowe generowanie sygnału DMX512 itp.). **Takie niedogodności nie występują w bramce PROMYK 3.60 która działa stabilnie w sieciach Ethernet**, dzięki czemu początkujący użytkownicy mogą skupić się na nauce tworzenia efektów świetlnych bez konieczności rozwiązywania problemów technicznych.
  * Bramka Artnet **PROMYK 3.60** jest przystępna cenowo, co czyni ją atrakcyjnym wyborem dla osób poszukujących ekonomicznego rozwiązania do przesyłania sygnałów DMX przez sieć Ethernet.
  * Bramki Artnet **PROMYK x.xx** są produktami powstającymi w Polsce i renomę uzyskały dzięki stabilności działania, prostocie obsługi oraz przystępnej cenie w porównaniu do konkurencyjnych rozwiązań. Uzyskały zaufanie zarówno wśród profesjonalistów jak i amatorów zajmujących się oświetleniem scenicznym bez sponsorowanych recenzji. 
  
  **Instrukcje i dokumentacja techniczna bramki Artnet PROMYK 3.60 są dostępne na stronie firmowej WKL TEAM64 pod adresem: [https://wklteam64.github.io](https://wklteam64.github.io) oraz na stronie firmowej** [https://wklteam64.pl](https://wklteam64.pl) **w zakładce "do pobrania".**