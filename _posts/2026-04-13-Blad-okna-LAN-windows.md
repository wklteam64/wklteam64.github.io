---
layout: post
title: Błędne działanie okna "Edytowanie Ustawień protokołu IP" w systemie Windows
author: WKL TEAM64
---

## Wprowadzenie

Konfiguracja bramki ARTNET PROMYK 3.60 jest bardzo prosta i jest formalnością czego dowodem są instrukcje i filmy instruktażowe dostępne na tej stronie statycznej dokumentacji. Czasem jednak zdarza się że użytkownik ma problem z konfiguracją i nie jest w stanie znaleźć przyczyny błędnego działania mimo że postępuje zgodnie z instrukcjami.

![okno protokolu](https://wklteam64.github.io/img/editErr.webp)

Takim przykładem jest błąd w oknie **"Edytowanie Ustawień protokołu IP"**. Przyczyną tego błędu jest błąd Windowsa i należy przejść innego okna do konfiguracji protokołu IP.

## Rozwiązanie problemu 

Aby rozwiązać ten problem należy przejść do **"Centrum sieci i udostępniania"** i kliknąć w **"Zmień ustawienia karty sieciowej"**. Następnie należy kliknąć prawym przyciskiem myszy na kartę sieciową i wybrać **"Właściwości"**. W oknie właściwości należy znaleźć **"Protokół internetowy w wersji 4 (TCP/IPv4)"** i kliknąć na niego dwukrotnie. W ten sposób otworzy się okno konfiguracji protokołu IP, które powinno działać poprawnie.

![okno protokolu](https://wklteam64.github.io/img/konfWlascIpv4a192168130.webp)

Przykład na obrazku dotyczy konfiguracji adresu IP dla ustawień fabrycznych bramki ARTNET PROMYK 3.60, czyli adresu IP  192.168.1.30 maska 255.255.255.0 , Universe 0 w gnieździe DX0 i Universe 1 w gnieździe DX1.

> Częstym błędem mimo sygnalizowania tego w instrukcjach jest wpisawanie adresu IP tego samego co bramka, czyli 192.168.1.30 zamiast 192.168.1.1 lub 192.168.1.2 w ustawieniach karty sieciowej. Należy pamiętać że adres IP karty sieciowej musi być inny niż adres IP bramki, ale musi być w tej samej podsieci, czyli 192.168.1.x gdzie x to liczba od 1 do 254 z wyłączeniem 30.

Przykład konfiguracji zaczyna się od 2:55

[![Uruchomienie bramki Artnet PROMYK 3.60 w 30 sekund w systemie Windows](https://wklteam64.github.io/img/yt.webp)](https://youtu.be/WJkzyEks0rM?si=frQuHU7rry48ImgK)
 
W filmowym przykładzie pokazano jak skonfigurować bramkę ARTNET PROMYK 3.60 w systemie Windows dla sieci natywnej ARTNET, czyli 2.0.0.0/8, 

![okno protokołu 2.0.0.0/8](https://wklteam64.github.io/img/WethKonf.webp)

Karta sieciowa  LAN komputera została skonfigurowana z adresem IP **2.0.0.2 z maską 255.0.0.0** w skrócie **2.0.0.2/8** a bramka ARTNET PROMYK 3.60 została skonfigurowana z adresem IP **2.168.1.30/8**. W ten sposób komputer i bramka są w tej samej podsieci i mogą się komunikować bez problemów.

> Koncepcja strony konfiguracyjnej www bramki ARTNET PROMYK 3.60 jest taka że może służyć do zmiany konfiguracji urządzenia jak i sprawdzenia  czy urządzenie jest dostępne w sieci. Jeśli strona konfiguracyjna jest niedostępna to oznacza że bramka może nie być dostępna w sieci, co może być spowodowane błędną konfiguracją adresu IP karty sieciowej lub bramki, lub problemem z połączeniem sieciowym. Tak więc jeśli nie potrzebuje się zmieniać konfiguracji bramki i jednocześnie istnieje pewność poprawności konfiguracji można przejść od razu aplikacji DMX512 i tam to sprawdzić poprzez odbiór pakietów ARTNET. Jeśli aplikacja DMX512 nadaje pakiety na UNiverse zgodny z konfiguracją bramki to odpowiednio będzie to sygnalizowane diodami LED  na złączach DX0 i DX1.

Oprócz tego w **CMD** lub **PowerShell** można użyć komendy **ipconfig** a potem **ping** do sprawdzenia czy bramka jest dostępna w sieci. 

![Ipconfig](https://wklteam64.github.io/img/Wipcon.webp)

Na przykład, jeśli bramka ma adres IP 2.168.1.30, to można użyć komendy **ping 2.168.1.30** w terminalu.

![ping 2.168.1.30](https://wklteam64.github.io/img/ping200.webp)

> Sens używania komend w **CMD** lub **PowerShell** jest taki że można szybko sprawdzić czy bramka jest dostępna w sieci.Jeśli ping zwraca odpowiedź, to oznacza że bramka jest dostępna i można przejść do dalszej konfiguracji lub testowania. Jeśli ping zwraca błąd, to oznacza że bramka może być niedostępna w sieci, co może być spowodowane błędną konfiguracją adresu IP karty sieciowej lub bramki, lub problemem z połączeniem sieciowym. Poza tym ta metoda jest szybsza niż szukanie informacji porzez okna WINDOWS i jest bardziej uniwersalna, ponieważ działa na wszystkich systemach operacyjnych WINDOWS, które obsługują protokół TCP/IP.